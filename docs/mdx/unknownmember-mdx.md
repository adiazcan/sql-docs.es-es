---
title: UnknownMember (MDX) | Documentos de Microsoft
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 84eda6f42b674ebde8793605816f98e82af350d8
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34743364"
---
# <a name="unknownmember-mdx"></a>UnknownMember (MDX)


  Devuelve el miembro desconocido asociado con un nivel o miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Member expression syntax  
Member_Expression.UnknownMember  
  
Hierarchy_expression syntax  
Hierarchy_Expression.UnknownMember  
```  
  
## <a name="arguments"></a>Argumentos  
 *Expresión_miembro*  
 Expresión MDX válida que devuelve un miembro.  
  
 *Hierarchy_Expression*  
 Expresión MDX válida que devuelve una jerarquía.  
  
## <a name="remarks"></a>Notas  
 Analysis Services crea un miembro desconocido para asociar los datos de la tabla de hechos con una jerarquía cuando no se conoce la jerarquía. El miembro desconocido puede hallarse en cualquiera de los niveles siguientes:  
  
-   En el nivel superior de las jerarquías de atributo que no se agregan.  
  
-   En el primer nivel por debajo del **todos los** nivel para jerarquías naturales.  
  
-   En cualquier nivel en el caso de las jerarquías no naturales.  
  
 Si se especifica una expresión de miembro, el **UnknownMember** función devuelve el miembro desconocido miembro secundario del miembro especificado. Si el miembro especificado no existe, la función devuelve un valor NULL.  
  
 Si se especifica una expresión de jerarquía, el **UnknownMember** función devuelve el miembro desconocido en el nivel superior, si existe alguno.  
  
 Si el miembro desconocido no existe en el nivel o miembro, el **UnknownMember** función crea un miembro con valor null.  
  
> [!NOTE]  
>  Si el miembro desconocido no existe en la jerarquía o el miembro, se genera un error.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente devuelve el miembro desconocido del miembro All Products de la jerarquía de atributo Product de todos los miembros de la dimensión Measures.  
  
```  
SELECT [Product].[Product].[All Products].UnknownMember  
    ON Columns,  
[Measures].Members  
    ON Rows  
FROM [Adventure Works]  
  
```  
  
 El ejemplo siguiente devuelve el miembro desconocido de la jerarquía Product Categories de todos los miembros de la dimensión Measures.  
  
```  
SELECT [Product].[Product Categories].UnknownMember  
    ON Columns,  
[Measures].Members  
    ON Rows  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
