---
title: Resumen del modelo de objetos de RDS | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS objects [ADO], object model summary
- RDS object model [ADO]
ms.assetid: 909f9af7-31db-4eec-ad52-650ce74dac2f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0421f5eead03d6e3641054b9c26dc1d4dac838e6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47822135"
---
# <a name="rds-object-model-summary"></a>Resumen del modelo de objetos de RDS
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, componentes de servidor RDS ya no están incluidos en el sistema operativo de Windows (consulte Windows 8 y [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) para obtener más detalles). Componentes de cliente RDS se quitará en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Deben migrar las aplicaciones que usan RDS a [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
|Objeto|Descripción|  
|------------|-----------------|  
|[RDS. Espacio de datos](../../../ado/reference/rds-api/dataspace-object-rds.md)|Este objeto contiene un método para obtener a un servidor proxy. El proxy puede ser el valor predeterminado o un programa de servidor personalizado (objeto de negocios). El programa de servidor puede invocarse en Internet, intranet, una red de área local, o puede ser una biblioteca de vínculos dinámicos local.<br /><br /> El **DataSpace** objeto es seguro para scripting.|  
|[RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|Este objeto representa el programa de servidor predeterminado. Ejecuta el comportamiento predeterminado de RDS datos recuperación y actualización.<br /><br /> El **DataFactory** objeto no es seguro para scripting.|  
|[RDS. Control de datos](../../../ado/reference/rds-api/datacontrol-object-rds.md)|Este objeto puede invocar automáticamente la **RDS. DataSpace** y **RDSServer.DataFactory** objetos.<br /><br /> Utilice este objeto para invocar el comportamiento de recuperación y actualización de datos RDS de forma predeterminada.<br /><br /> Este objeto también proporciona los medios para controles visuales tener acceso a la devuelta **Recordset** objeto.<br /><br /> El **DataControl** objeto es seguro para scripting.|  
  
## <a name="see-also"></a>Vea también  
 [Conceptos básicos de RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)   
 [Escenario RDS](../../../ado/guide/remote-data-service/rds-scenario.md)   
 [Tutorial de RDS](../../../ado/guide/remote-data-service/rds-tutorial.md)   
 [Seguridad y uso de RDS](../../../ado/guide/remote-data-service/rds-usage-and-security.md)


