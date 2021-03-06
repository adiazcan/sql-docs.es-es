---
title: Consulta de elemento (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 861f216ac263de32b9f2afc3e0fcd4e43b3dfb4a
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "37984646"
---
# <a name="query-element-xmla"></a>Elemento Query (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contiene una consulta dentro de la [consultas](../../../analysis-services/xmla/xml-elements-properties/queries-element-xmla.md) colección usada por el [DesignAggregations](../../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md) comando durante la optimización basada en uso.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Queries>  
   ...  
   <Query>...</Query>  
   ...  
</Queries>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|String|  
|Valor predeterminado|None|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer una y solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones de elementos  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[Consultas](../../../analysis-services/xmla/xml-elements-properties/queries-element-xmla.md)|  
|Elementos secundarios|None|  
  
## <a name="remarks"></a>Notas  
 El comando **DesignAggregations** admite la optimización basada en el uso incluyendo uno o más elementos **Query** en la colección **Queries** del comando. Cada elemento **Query** representa una consulta de objetivo que utiliza el proceso de diseño para definir agregaciones dirigidas a las consultas utilizadas con más frecuencia. Puede especificar sus propias consultas de objetivo, o puede usar la información almacenada por una instancia de Analysis Services en el registro de consultas para recuperar información acerca de las consultas utilizadas con frecuencia.  
  
 Si está diseñando agregaciones de forma iterativa, solo tiene que pasar las consultas de objetivo en la primera **DesignAggregations** comando porque el [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia almacena estas consultas de objetivo y las usa durante la subsiguiente  **DesignAggregations** comandos. Después de incluir las consultas del objetivo en el primer comando **DesignAggregations** de un proceso iterativo, cualquier comando **DesignAggregations** posterior que contenga las consultas de objetivo en la propiedad **Queries** generará un error.  
  
 El elemento **Query** contiene un valor delimitado por comas que contiene los siguientes argumentos:  
  
 *Frequency*,*Dataset*[,*Dataset*...]  
  
 *Frecuencia*  
 Un factor de ponderación que corresponde al número de veces que se ha ejecutado con anterioridad la consulta. Si el elemento **Query** representa una nueva consulta, el valor *Frequency* representa el factor de ponderación utilizado por el proceso del diseño para evaluar la consulta. A medida que el valor de frecuencia se vuelve mayor, el valor de ponderación que se asigna a la consulta durante el proceso de diseño va aumentando.  
  
 *Conjunto de datos*  
 Una cadena numérica que especifica qué atributos de una dimensión se van a incluir en la consulta. Esta cadena debe tener el mismo número de caracteres que el número de atributos de la dimensión. El cero (0) indica que el atributo de la posición ordinal especificada no está incluido en la consulta de la dimensión especificada, mientras que el uno (1) indica que el atributo de la posición ordinal especificada está incluido en la consulta de la dimensión especificada.  
  
 Por ejemplo, la cadena "011" haría referencia a una consulta que implicaría una dimensión con tres atributos, de los que el segundo y el tercero estarían incluidos en la consulta.  
  
> [!NOTE]  
>  Algunos atributos no se tienen en cuenta en el conjunto de datos. Para obtener más información sobre los atributos excluidos, vea [Properties (XMLA)](../../../analysis-services/xmla/xml-elements-properties/query-element-xmla.md).  
  
 Cada dimensión del grupo de medida que contiene el diseño de agregaciones está representada por un valor *Dataset* en el elemento **Query** . El orden de los valores de *Dataset* debe coincidir con el orden de las dimensiones incluidas en el grupo de medidas.  
  
## <a name="see-also"></a>Vea también
 [Diseño de agregaciones &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/designing-aggregations-xmla.md)   
 [Propiedades &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
