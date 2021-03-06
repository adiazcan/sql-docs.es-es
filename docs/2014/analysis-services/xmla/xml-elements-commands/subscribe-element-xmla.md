---
title: Elemento Subscribe (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Subscribe Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Subscribe
- microsoft.xml.analysis.subscribe
- http://schemas.microsoft.com/analysisservices/2003/engine#Subscribe
helpviewer_keywords:
- Subscribe command
ms.assetid: aad50dd7-44d4-4d83-a973-187f9aed35ec
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: cf88b3e4e2fd990ad786b8e505c908f96f53ce6e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48079345"
---
# <a name="subscribe-element-xmla"></a>Elemento Subscribe (XMLA)
  Se suscribe a un seguimiento y devuelve un conjunto de filas que contiene los eventos de seguimiento desde un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Command>  
   <Subscribe>  
      <Object>...</Object>  
   </Subscribe>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|None|  
|Valor predeterminado|None|  
|Cardinalidad|0-n: elemento opcional que puede aparecer más de una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Elementos secundarios|[Objeto](../xml-elements-properties/object-element-xmla.md)|  
  
## <a name="remarks"></a>Comentarios  
 El `Subscribe` comando se suscribe a y secuencias devuelve un conjunto de filas de un seguimiento especificado en un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia. Si se especifica un objeto que no sea un seguimiento en el `Object` elemento, que se produce un error.  
  
 Si no se especifica el elemento `Object`, se define un seguimiento de la sesión, a la que se suscribe, en la instancia [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. El seguimiento de la sesión devuelve un conjunto fijo de eventos de seguimiento desde la sesión actual.  
  
 El flujo de conjunto de filas devuelto por este comando se interrumpe si la aplicación cliente cierra la conexión con el [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia, o si la sesión en el que el `Subscribe` se ejecuta el comando finaliza.  
  
## <a name="see-also"></a>Vea también  
 [Comandos &#40;XMLA&#41;](xml-elements-commands.md)  
  
  
