---
title: Actualizar bases de datos replicadas | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- merge replication database upgrades [SQL Server replication]
- replication [SQL Server], upgrading
- transactional replication, upgrading databases
- snapshot replication [SQL Server], upgrading databases
- upgrading replicated databases
ms.assetid: 9926a4f7-bcd8-4b9b-9dcf-5426a5857116
author: MashaMSFT
ms.author: mathoma
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
manager: craigg
ms.openlocfilehash: c92626c8ef9e24436c323819ca50c211aead9ffb
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699743"
---
# <a name="upgrade-replicated-databases"></a>Actualizar bases de datos replicadas

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  
  [!INCLUDE[ssNoversion](../../includes/ssnoversion-md.md)] admite la actualización de bases de datos replicadas desde versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; no es necesario detener la actividad en otros nodos mientras se actualiza un nodo. Asegúrese de cumplir las reglas relativas a la versión admitida en una topología:  
  
-   Un distribuidor puede ser de cualquier versión siempre que ésta sea mayor o igual que la versión del publicador (en muchos casos el distribuidor es la misma instancia que el publicador).  
  
-   Un publicador puede ser de cualquier versión siempre que ésta sea menor o igual que la versión del distribuidor.  
  
-   La versión del suscriptor depende del tipo de publicación:  
  
    -   Un suscriptor de una publicación transaccional puede ser de cualquiera de las dos versiones del publicador. Por ejemplo, un publicador de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] puede tener suscriptores de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] y [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] , y un publicador de [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] puede tener suscriptores de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] y  [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .  
  
    -   Un suscriptor de una publicación de combinación puede ser de cualquier versión menor o igual que la versión del publicador.  
  
> [!NOTE]  
>  Este artículo está disponible en la documentación de la Ayuda del programa de instalación y en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. los vínculos de artículos que aparecen en negrita en la documentación de la Ayuda del programa de instalación hacen referencia a artículos que solo se encuentran disponibles en los Libros en pantalla. **Puede diseñar una estrategia de actualización para el publicador, el suscriptor y el distribuidor con las opciones descritas en esta [entrada de blog](https://blogs.msdn.microsoft.com/sql_server_team/upgrading-a-replication-topology-to-sql-server-2016/)**. 
  
## <a name="run-the-log-reader-agent-for-transactional-replication-before-upgrade"></a>Ejecutar el Agente de registro del LOG para la replicación transaccional antes de la actualización  
 Antes de actualizar a [!INCLUDE[ssNoversion](../../includes/ssnoversion-md.md)], debe asegurarse de que el Agente de registro del LOG ha procesado todas las transacciones confirmadas en las tablas publicadas. Para asegurarse de que se han procesado todas las transacciones, siga estos pasos para cada base de datos que contenga publicaciones transaccionales:  
  
1.  Asegurarse de que el Agente de registro del LOG se está ejecutando para la base de datos. De forma predeterminada, el agente se ejecuta sin interrupción.  
  
2.  Detenga la actividad de usuario en las tablas publicadas.  
  
3.  Deje tiempo para que el Agente de registro del LOG copie las transacciones en la base de datos de distribución y, a continuación, detenga el agente.  
  
4.  Ejecute [sp_replcmds](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md) para comprobar que se han procesado todas las transacciones. El conjunto de resultados de este procedimiento debe estar vacío.  
  
5.  Ejecute [sp_replflush](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md) para cerrar la conexión de sp_replcmds.  
  
6.  Realice la actualización del servidor a la versión más reciente de [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)].  
  
7.  Reinicie el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el Agente de registro del LOG si no se inician automáticamente después de la actualización.  
  
## <a name="run-agents-for-merge-replication-after-upgrade"></a>Ejecutar agentes para la replicación de mezcla después de la actualización  
 Después de la actualización, ejecute el Agente de instantáneas de cada publicación de combinación y el Agente de mezcla de cada suscripción para actualizar los metadatos de la replicación. No tiene que aplicar la nueva instantánea porque no es necesaria para reinicializar las suscripciones. Los metadatos de suscripción se actualizan la primera vez que el Agente de mezcla se ejecuta tras la actualización. Esto significa que la base de datos de suscripciones puede permanecer en línea y activa durante la actualización del publicador.  
  
 La replicación de mezcla almacena metadatos de publicación y suscripción en un determinado número de tablas del sistema en las bases de datos de publicaciones y suscripciones. La ejecución del Agente de instantáneas actualiza los metadatos de publicación y la ejecución del Agente de mezcla actualiza los metadatos de suscripción. Solo es necesaria para generar una instantánea de publicación. Si una publicación de combinación utiliza filtros con parámetros, cada partición también tendrá una instantánea. No es necesario actualizar estas instantáneas con particiones.  
  
 Ejecute los agentes desde [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], el Monitor de replicación o la línea de comandos. Para más información sobre la ejecución del Agente de instantáneas, vea estos artículos:  
  
-   [Crear y aplicar la instantánea inicial](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)  
  
-   [Crear y aplicar la instantánea inicial](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [Conceptos de los ejecutables del Agente de replicación](../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
  
 Para más información sobre la ejecución del Agente de mezcla, vea estos artículos:  
  
-   [Sincronizar una suscripción de extracción](../../relational-databases/replication/synchronize-a-pull-subscription.md)  
  
-   [Sincronizar una suscripción de inserción](../../relational-databases/replication/synchronize-a-push-subscription.md)  
  
 Después de actualizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una topología que utiliza la replicación de mezcla, cambie el nivel de compatibilidad de publicación de todas las publicaciones si desea utilizar nuevas características.  
  
## <a name="upgrading-to-standard-workgroup-or-express-editions"></a>Actualizar a Standard Edition, Workgroup Edition o Express Edition  
 Antes de actualizar desde una edición de [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] a otra, compruebe que las funciones que actualmente usa son compatibles con la edición a la que quiere actualizar. Para más información, vea la sección sobre replicación de [Ediciones y características admitidas de SQL Server](../../sql-server/editions-and-components-of-sql-server-2017.md).  
  
## <a name="web-synchronization-for-merge-replication"></a>Sincronización web para la replicación de mezcla  
 La opción de sincronización web para replicación de mezcla requiere que se copie el archivo Escucha de replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (replisapi.dll) en el directorio virtual del servidor de Internet Information Services (IIS) que se usa para la sincronización. Cuando se configura la sincronización web, se copia el archivo en el directorio virtual mediante el Asistente para configurar la sincronización web. Si se actualizan los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalados en el servidor IIS, debe copiarse manualmente el archivo replisapi.dll del directorio COM en el directorio virtual del servidor IIS. Para obtener más información sobre cómo configurar la sincronización web, vea [Configurar la sincronización web](../../relational-databases/replication/configure-web-synchronization.md).  
  
## <a name="restoring-a-replicated-database-from-an-earlier-version"></a>Restaurar una base de datos replicada a partir de una versión anterior  
 Para asegurarse de que la configuración de replicación se conserva al restaurar una copia de seguridad de una base de datos replicada a partir de una versión anterior, restaure en un servidor y una base de datos con los mismos nombres que el servidor y la base de datos donde se realizó la copia de seguridad.  
  
## <a name="see-also"></a>Ver también  
 [Administración &#40;replicación&#41;](../../relational-databases/replication/administration/administration-replication.md)   
 [Compatibilidad con versiones anteriores de replicación](../../relational-databases/replication/replication-backward-compatibility.md)   
 [Novedades &#40;Replicación&#41;](../../relational-databases/replication/what-s-new-replication.md)   
 [Actualizaciones de ediciones y versiones admitidas](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)   
 [Actualizar SQL Server](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
