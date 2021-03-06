---
title: Elemento Parameters (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 68366f03168b7c7c434f05e88f512401248c1124
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38050452"
---
# <a name="parameters-element-xmla"></a>Elemento Parameters (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contiene una colección de [parámetro](../../../analysis-services/xmla/xml-elements-properties/parameter-element-xmla.md) elementos utilizados por el [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) método.  
  
 **Namespace:** `urn:schemas-microsoft-com:xml-analysis`  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<Execute>  
...  
   <Parameters>  
      <Parameter>...</Parameter>  
   </Parameters>  
...  
</Execute>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|None|  
|Valor predeterminado|None|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer una y solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones de elementos  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[Ejecutar](../../../analysis-services/xmla/xml-elements-methods-execute.md)|  
|Elementos secundarios|[Parámetro](../../../analysis-services/xmla/xml-elements-properties/parameter-element-xmla.md)|  
  
## <a name="remarks"></a>Notas  
 Alguna parte del código XML para los comandos de Analysis (XMLA), como el comando [Process](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) , puede requerir información adicional. El **parámetros** elemento proporciona un mecanismo para ofrecer información adicional, incluso información en lotes, para un comando XMLA.  
  
 Si el comando XMLA no utiliza el **parámetros** elemento, se puede omitir el elemento cuando se llama a la **Execute** método.  
  
## <a name="see-also"></a>Vea también
 [Propiedades &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
