---
title: Jobs (objeto del Agente SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: f21be22ec5020a7863d4bfcd3e49f2a58df09463
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47676725"
---
# <a name="sql-server-agent-jobs-object"></a>Jobs (objeto del Agente SQL Server)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  El objeto de rendimiento **Jobs** del Agente SQL Server contiene contadores de rendimiento que proporcionan información acerca de los trabajos del Agente SQL Server. En la siguiente tabla se enumeran los contadores incluidos en este objeto.  
  
 La tabla siguiente contiene los contadores de **SQLAgent:Jobs** .  
  
|Nombre|Descripción|  
|----------|-----------------|  
|**Trabajos activos**|Este contador muestra el número de trabajos que se están ejecutando.|  
|**Trabajos con error**|Este contador muestra el número de trabajos que han terminado con un error.|  
|**Tasa de trabajos con éxito**|Este contador muestra el porcentaje de trabajos ejecutados que se han completado con éxito.|  
|**Trabajos activados/minuto**|Este contador muestra el número de trabajos que se han iniciado en el último minuto.|  
|**Trabajos en cola**|Este contador muestra el número de trabajos preparados para que el Agente SQL Server pueda ejecutarlos, pero que aún no se están ejecutando.|  
|**Trabajos con éxito**|Este contador muestra el número de trabajos que han terminado con éxito.|  
  
 Cada contador del objeto contiene las instancias siguientes:  
  
|Instancia|Descripción|  
|--------------|-----------------|  
|**_Total**|Información para todos los trabajos.|  
|**Alertas**|Información de los trabajos iniciados por las alertas.|  
|**Otros**|Información de los trabajos no iniciados por alertas ni programaciones. Normalmente estos trabajos de inician de forma manual mediante **sp_start_job**.|  
|**Programaciones**|Información de los trabajos iniciados por las programaciones.|  
  
## <a name="see-also"></a>Ver también  
 [Implementar trabajos](../../ssms/agent/implement-jobs.md)   
 [Usar objetos de rendimiento](../../ssms/agent/use-performance-objects.md)   
 [Supervisar el uso de recursos&#40;Monitor de sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
