---
title: FeatureSet (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 7f489fba4c9ea113cffd608b496d04448399481a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48191585"
---
# <a name="featureset-element-dta"></a>FeatureSet (DTA, elemento)
  Contiene las estructuras de diseño físico (índices o vistas indizadas) que desea que utilice el Asistente para la optimización de motor de base de datos durante el análisis.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|**Tipo y longitud de los datos**|`string`, sin longitud máxima.|  
|**Valores permitidos**|**IDX_IV**<br /> Índices y vistas indizadas.<br /><br /> **IDX**<br /> Solo índices.<br /><br /> **IV**<br /> Solo vistas indizadas.<br /><br /> **NCL_IDX**<br /> Solo índices no clúster.<br /><br /> Utilice uno de estos valores con este elemento.|  
|**Valor predeterminado**|**IDX**|  
|**Repetición**|Una obligatoria para cada elemento `TuningOptions`, a menos que se utilice el elemento `DropOnlyMode`. Si `DropOnlyMode` es utilizado, no se puede usar `FeatureSet`. Estos elementos son mutuamente exclusivos.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elementos|  
|------------------|--------------|  
|**Elemento primario**|[TuningOptions, elemento &#40;DTA&#41;](tuningoptions-element-dta.md)|  
|**Elementos secundarios**|Ninguno.|  
  
## <a name="example"></a>Ejemplo  
 Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
