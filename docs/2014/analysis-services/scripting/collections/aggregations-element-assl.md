---
title: Elemento Aggregations (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Aggregations Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Aggregations
helpviewer_keywords:
- Aggregations element
ms.assetid: 79b7de7a-53b2-4202-bc0f-de1daaf1b179
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2d64819bb59cbd86b2179abfbfd3afb5639577a0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48177595"
---
# <a name="aggregations-element-assl"></a>Elemento Aggregations (ASSL)
  Contiene la colección de agregaciones definida para un [AggregationDesign](../objects/aggregationdesign-element-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<AggregationDesign>  
   ...  
   <Aggregations>  
      <Aggregation>...</Aggregation>  
   </Aggregations>  
   ...  
</AggregationDimension>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|Ninguno (colección)|  
|Valor predeterminado|Ninguno (colección)|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer una y solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elemento primario|[Elemento AggregationDesign](../objects/aggregationdesign-element-assl.md)|  
|Elementos secundarios|[agregación](../objects/aggregation-element-assl.md)|  
  
## <a name="remarks"></a>Comentarios  
 El elemento correspondiente en el modelo de objetos de Analysis Management Objects (AMO) es <xref:Microsoft.AnalysisServices.AggregationCollection>.  
  
## <a name="see-also"></a>Vea también  
 [Elemento MeasureGroup &#40;ASSL&#41;](../objects/group-element-assl.md)   
 [Elemento de la partición &#40;ASSL&#41;](../objects/partition-element-assl.md)   
 [Colecciones &#40;ASSL&#41;](collections-assl.md)  
  
  
