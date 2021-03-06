---
title: Restaurar una base de datos en el clúster de macrodatos de SQL Server | Microsoft Docs
description: En este artículo se muestra cómo restaurar una base de datos en la instancia principal de un clúster de macrodatos de SQL Server.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 10/09/2018
ms.topic: conceptual
ms.prod: sql
ms.openlocfilehash: e921948cb5dcd0bda52ed9ebcc07c8a2496611ff
ms.sourcegitcommit: 110e5e09ab3f301c530c3f6363013239febf0ce5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2018
ms.locfileid: "48905055"
---
# <a name="restore-a-database-into-the-sql-server-big-data-cluster-master-instance"></a>Restaurar una base de datos en la instancia maestra del clúster de SQL Server datos de gran tamaño

En este artículo se describe cómo restaurar una base de datos existente en la instancia principal de un clúster de macrodatos de 2019 de SQL Server (versión preliminar). El método recomendado es usar una copia de seguridad y restaurar el enfoque.

## <a name="backup-your-existing-database"></a>Copia de seguridad de la base de datos existente

En primer lugar, copia de seguridad de la base de datos de SQL Server existente de SQL Server en Windows o Linux. Use las técnicas estándar de copia de seguridad con Transact-SQL o con una herramienta como SQL Server Management Studio (SSMS).

En este artículo se muestra cómo restaurar la base de datos de AdventureWorks, pero puede utilizar cualquier copia de seguridad de base de datos. 

> [!TIP]
> Puede descargar la copia de seguridad de AdventureWorks [aquí](https://www.microsoft.com/en-us/download/details.aspx?id=49502).

## <a name="copy-the-backup-file"></a>Copie el archivo de copia de seguridad

Copie el archivo de copia de seguridad en el contenedor de SQL Server en el pod de la instancia maestra del clúster de Kubernetes.

```bash
kubectl cp <path to .bak file> mssql-master-pool-0:/tmp -c mssql-server -n <name of your cluster>
```

Ejemplo:

```bash
kubectl cp ~/Downloads/AdventureWorks2016CTP3.bak mssql-master-pool-0:/tmp -c mssql-server -n clustertest
```

A continuación, compruebe que se copió el archivo de copia de seguridad en el contenedor de pod.

```bash
kubectl exec -it mssql-master-pool-0 -n <name of your cluster> -c mssql-server -- bin/bash
cd /var/
ls /tmp
exit
```

Ejemplo:

```bash
kubectl exec -it mssql-master-pool-0 -n clustertest -c mssql-server -- bin/bash
ls /tmp
exit
```

## <a name="restore-the-backup-file"></a>Restaurar el archivo de copia de seguridad

A continuación, restaure la copia de seguridad de base de datos a la instancia principal de SQL Server.  Si va a restaurar una copia de seguridad de base de datos que se creó en Windows, deberá obtener los nombres de los archivos.  En Azure Data Studio, conéctese a la instancia maestra y ejecute este script de SQL:

```sql
RESTORE FILELISTONLY FROM DISK='/tmp/<db file name>.bak'
```

Ejemplo:

```sql
RESTORE FILELISTONLY FROM DISK='/tmp/AdventureWorks2016CTP3.bak'
```

![Lista de archivos de copia de seguridad](media/restore-database/database-restore-file-list.png)

Ahora, restaure la base de datos. El script siguiente es un ejemplo. Reemplace los nombres o rutas de acceso según sea necesario según la copia de seguridad de base de datos.

```sql
RESTORE DATABASE AdventureWorks2016CTP3
FROM DISK='/tmp/AdventureWorks2016CTP3.bak'
WITH MOVE 'AdventureWorks2016CTP3_Data' TO '/var/opt/mssql/data/AdventureWorks2016CTP3_Data.mdf',
        MOVE 'AdventureWorks2016CTP3_Log' TO '/var/opt/mssql/data/AdventureWorks2016CTP3_Log.ldf',
        MOVE 'AdventureWorks2016CTP3_mod' TO '/var/opt/mssql/data/AdventureWorks2016CTP3_mod'
```

## <a name="configure-data-pool-and-hdfs-access"></a>Configurar el grupo de datos y acceso HDFS

Ahora, para la instancia de SQL Server maestra a los grupos de datos de access y HDFS, ejecute los procedimientos de grupo almacenado de grupo y el almacenamiento de datos. Ejecute los siguientes scripts de Transact-SQL en la base de datos recién restaurada:

```sql
USE AdventureWorks2016CTP3
GO 
IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlDataPool')
    CREATE EXTERNAL DATA SOURCE SqlDataPool
    WITH (LOCATION = 'sqldatapool://service-mssql-controller:8080/datapools/default');

IF NOT EXISTS(SELECT * FROM sys.external_data_sources WHERE name = 'SqlStoragePool')
    CREATE EXTERNAL DATA SOURCE SqlStoragePool
    WITH (LOCATION = 'sqlhdfs://service-mssql-controller:8080');
GO
```

> [!NOTE]
> Tendrá que ejecutar a través de estas secuencias de comandos del programa de instalación sólo para bases de datos restauradas desde versiones anteriores de SQL Server. Si crea una nueva base de datos en la instancia principal de SQL Server, procedimientos de almacén de grupo de grupo y el almacenamiento datos ya están configurados para usted.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información acerca de los clústeres de macrodatos de SQL Server, consulte la información general siguiente:

- [¿Qué es SQL Server 2019 macrodatos clústeres?](big-data-cluster-overview.md)
