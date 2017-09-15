---
title: SET STATISTICS XML (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SET_STATISTICS_XML_TSQL
- SET STATISTICS XML
dev_langs:
- TSQL
helpviewer_keywords:
- statistical information [SQL Server], statement processing
- STATISTICS XML option
- SET STATISTICS XML statement
- statements [SQL Server], statistical information
- XML [SQL Server], statement execution information
ms.assetid: 2b6d4c5a-a7f5-4dd1-b10a-7632265b1af7
caps.latest.revision: 40
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 45191a544866451e5208325eb2cafcab60bc8fb5
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="set-statistics-xml-transact-sql"></a>SET STATISTICS XML (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Hace que Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecute instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y genere información detallada sobre cómo se ejecutaron las instrucciones en un documento XML definido correctamente.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
SET STATISTICS XML { ON | OFF }  
```  
  
## <a name="remarks"></a>Comentarios  
 El valor de SET STATISTICS XML se establece en tiempo de ejecución, no en tiempo de análisis.  
  
 Si SET STATISTICS XML es ON, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelve información sobre la ejecución de cada instrucción después de ejecutarla. Cuando esta opción está establecida en ON, se devuelve información acerca de todas las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes hasta que se vuelve a establecer en OFF. Tenga en cuenta que SET STATISTICS XML no tiene que ser la única instrucción de un lote.  
  
 SET STATISTICS XML devuelve el resultado como **nvarchar (max)** para las aplicaciones, como el **sqlcmd** utilidad, donde la salida XML se utiliza otras herramientas para mostrar y procesar el plan de consulta información.  
  
 SET STATISTICS XML devuelve la información como un conjunto de documentos XML. Cada instrucción posterior a la instrucción SET STATISTICS XML ON se refleja en la salida con un solo documento. Cada documento contiene el texto de la instrucción, seguido de los detalles de los pasos de ejecución. La salida muestra información en tiempo de ejecución, como los costos, los índices a los que se ha tenido acceso, los tipos de operaciones realizadas, el orden de combinación, el número de veces que se realiza una operación física, el número de filas generadas por cada operador físico, etc.  
  
 El documento que contiene el esquema XML de la salida XML de SET STATISTICS XML se copia durante la instalación en un directorio local del equipo en el que se instala Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Se encuentra en la unidad que contiene los archivos de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], en:  
  
 \Microsoft SQL Server\100\Tools\Binn\schemas\sqlserver\2004\07\showplan\showplanxml.xsd  
  
 También puede encontrarse en el esquema del plan de presentación [este sitio Web](http://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).  
  
 SET STATISTICS PROFILE y SET STATISTICS XML son equivalentes. El primero genera resultados en formato de texto y el último en formato XML. En futuras versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la información del plan de ejecución de consultas se mostrará únicamente mediante la instrucción SET STATISTICS XML, no SET STATISTICS PROFILE.  
  
> [!NOTE]  
>  Si **incluir Plan de ejecución real** está seleccionado en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], esta opción SET no produce resultado del plan de presentación XML. Desactive el **incluir Plan de ejecución real** botón antes de utilizarla opción SET..  
  
## <a name="permissions"></a>Permissions  
 Para utilizar SET STATISTICS XML y ver el resultado, los usuarios deben tener los permisos siguientes:  
  
-   Los permisos adecuados para ejecutar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
-   El permiso SHOWPLAN para todas las bases de datos que contienen objetos a los que hacen referencia las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 Para las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que no generan conjuntos de resultados de STATISTICS XML, solo se necesitan los permisos adecuados para ejecutar las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)]. Para las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que generan conjuntos de resultados de STATISTICS XML, el permiso de ejecución de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] y el permiso SHOWPLAN deben ser correctos, o la ejecución de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] se anulará y no se generará información relativa al plan de presentación.  
  
## <a name="examples"></a>Ejemplos  
 Las dos instrucciones siguientes utilizan la opción SET STATISTICS XML para mostrar la forma en que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] analiza y optimiza el uso de índices en las consultas. La primera consulta utiliza el operador de comparación Es igual a (=) en la cláusula WHERE de una columna indizada. La segunda consulta utiliza el operador LIKE en la cláusula WHERE. De este modo, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe utilizar un recorrido de índice clúster para encontrar los datos que satisfacen la condición de la cláusula WHERE. Los valores de la **EstimateRows** y **EstimatedTotalSubtreeCost** atributos son inferiores en la primera consulta indizada que indica que se procesa mucho más rápido y utiliza menos recursos que el consultas no indizadas.  
  
```  
USE AdventureWorks2012;  
GO  
SET STATISTICS XML ON;  
GO  
-- First query.  
SELECT BusinessEntityID   
FROM HumanResources.Employee  
WHERE NationalIDNumber = '509647174';  
GO  
-- Second query.  
SELECT BusinessEntityID, JobTitle   
FROM HumanResources.Employee  
WHERE JobTitle LIKE 'Production%';  
GO  
SET STATISTICS XML OFF;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [SET SHOWPLAN_XML &#40;Transact-SQL&#41;](../../t-sql/statements/set-showplan-xml-transact-sql.md)   
 [sqlcmd (utilidad)](../../tools/sqlcmd-utility.md)  
  
  
