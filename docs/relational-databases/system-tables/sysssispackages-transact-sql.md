---
title: sysssispackages (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdtspackages90_TSQL
- sysdtspackages90
dev_langs:
- TSQL
helpviewer_keywords:
- sysssispackages system table
ms.assetid: 66155dcd-dcdb-4e33-a242-1625828ad8d2
author: douglasl
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7a1ab35e121683fd1c8d25dc21a2128aa3232c70
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47755089"
---
# <a name="sysssispackages-transact-sql"></a>sysssispackages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contiene una fila por cada paquete que se guarda en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Esta tabla se almacena en el **msdb** base de datos.  
  
  
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**Nombre**|**sysname**|Identificador único del paquete.|  
|**id**|**uniqueidentifier**|Identificador único global (GUID) del paquete.|  
|**Descripción**|**nvarchar**|Descripción opcional del paquete.|  
|**CREATEDATE**|**datetime**|Fecha de creación del paquete.|  
|**folderId**|**uniqueidentifier**|GUID de la carpeta lógica en la que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] incluye el paquete.|  
|**ownersid**|**varbinary**|Identificador de seguridad único del usuario que creó el paquete.|  
|**packagedata**|**imagen**|El paquete.|  
|**packageformat**|**int**|Formato con el que se guarda el paquete:<br /><br /> Un valor de 2 indica que el paquete se guarda en el [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] formato.<br /><br /> Un valor de 3 indica que el paquete se guarda en formato de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]o una versión posterior.|  
|**PackageType**|**int**|Cliente que creó el paquete. Los valores posibles son los siguientes:<br /><br /> 0 (valor predeterminado)<br /><br /> 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importar y exportar asistente)<br /><br /> 3 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replicación)<br /><br /> 5 ([!INCLUDE[ssIS](../../includes/ssis-md.md)] diseñador)<br /><br /> 6 (Asistente o Diseñador de planes de mantenimiento).<br /><br /> <br /><br /> Tenga en cuenta que los valores de esta columna se corresponden con los <xref:Microsoft.SqlServer.Dts.Runtime.DTSPackageType> enumeración.|  
|**VerMajor**|**int**|Última versión importante del paquete.|  
|**VerMinor**|**int**|Última versión de menor importancia del paquete.|  
|**verbuild**|**int**|Última versión de compilación del paquete.|  
|**vercomments**|**nvarchar**|Comentarios acerca de la versión del paquete.|  
|**Verid**|**uniqueidentifier**|El GUID de la versión del paquete.|  
|**IsEncrypted**|**bit**|Valor booleano que indica si el paquete está cifrado.|  
|**readrolesid**|**varbinary**|Rol de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que puede cargar paquetes.|  
|**writerolesid**|**varbinary**|Rol de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que puede guardar paquetes.|  
  
## <a name="see-also"></a>Vea también  
 [Paquetes de Integration Services &#40;SSIS&#41;](../../integration-services/integration-services-ssis-packages.md)  
  
  
