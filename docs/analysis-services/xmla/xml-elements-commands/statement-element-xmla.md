---
title: Elemento Statement (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 49238b50457a586bbf23cc75ee454003c57ac04e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "37979167"
---
# <a name="statement-element-xmla"></a>Elemento Statement (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contiene una consulta o instrucción se envíe mediante la **Execute** método a una instancia de Analysis Services.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Command>  
   <Statement>...</Statement>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|String|  
|Valor predeterminado|None|  
|Cardinalidad|0-n: elemento opcional que puede aparecer más de una vez.|  
  
## <a name="element-relationships"></a>Relaciones de elementos  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[Command](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Elementos secundarios|None|  
  
## <a name="remarks"></a>Notas  
 El **instrucción** comando ejecuta una consulta o instrucción en el [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia. [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] admite los lenguajes siguientes:  
  
-   Expresiones multidimensionales (MDX)  
  
-   Extensiones de minería de datos (MDX)  
  
-   Un subconjunto de Lenguaje de consulta estructurado (SQL)  
  
## <a name="see-also"></a>Vea también
 [Comandos &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  
