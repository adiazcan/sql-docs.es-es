---
title: Pestaña matriz de clasificación (vista Gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1879e9ec4f2a6decf4168e7c49a5e81d3a043d29
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48154715"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a>Pestaña Matriz de clasificación (vista Gráfico de precisión de minería de datos)
  La pestaña **Matriz de clasificación** muestra una matriz de clasificación para cada modelo seleccionado en la cuadrícula de modelos de la pestaña **Asignación de columnas** . La matriz de clasificación solo está disponible si la columna de predicción que está seleccionada en la pestaña **Asignación de columnas** no es continua. Para obtener una descripción más detallada de la pestaña **Matriz de clasificación** , vea [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).  
  
## <a name="options"></a>Opciones  
 **Copiar**  
 Copia el contenido de cada matriz de clasificación al portapapeles.  
  
 **Recuentos de \<modelo > en \< columna de predicción >**  
 Muestra una matriz de clasificación para cada modelo de minería de datos de la estructura de minería de datos. La matriz contiene las siguientes columnas:  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Puede predecir**|Contiene una fila de cada estado de la columna de predicción.|  
|**\<Estados > (real)**|Una columna para cada estado de la columna de predicción. Si el estado de la fila y la columna se corresponden, la celda representa el número de veces real que el estado existe en la base de datos. Si no se corresponden, la celda representa el error de la predicción.|  
  
## <a name="see-also"></a>Vea también  
 [Diseñador gráfico de precisión de minería de datos &#40;minería de datos&#41;](mining-accuracy-chart-designer-data-mining.md)   
 [Pruebas y validación tareas y procedimientos &#40;minería de datos&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md)   
 [Pruebas y validación &#40;minería de datos&#41;](data-mining/testing-and-validation-data-mining.md)  
  
  
