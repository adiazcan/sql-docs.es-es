---
title: Ampliar paquetes con Scripting | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- SQL Server Integration Services, scripting
- SSIS, scripting
- scripts [Integration Services], about scripting
ms.assetid: 67fe18ef-f3aa-41d4-9b9d-5defd4618c4b
caps.latest.revision: 40
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8ed9de3849d0c68af740d6256c53307f1606822a
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="extending-packages-with-scripting"></a>Ampliar paquetes con scripting
  Si los componentes integrados en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no cumplen sus requisitos, puede ampliar la eficacia de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] codificando sus propias extensiones. Cuenta con dos opciones diferenciadas para ampliar los paquetes: puede escribir código dentro de los potentes contenedores que proporcionan la tarea Script y el componente de script o puede crear extensiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizadas desde cero derivando de las clases base que proporciona el modelo de objetos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 En esta sección se explora la opción más sencilla de las dos, ampliar los paquetes con scripting.  
  
 La tarea Script y el componente de script permiten ampliar tanto el flujo de control como el flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con muy poca codificación. Ambos objetos utilizan el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] herramientas para el entorno de desarrollo de aplicaciones (VSTA) y la [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../includes/msconame-md.md)] los lenguajes de programación Visual C# y se benefician de toda la funcionalidad que ofrece el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] biblioteca de clases, así como ensamblados personalizados. La tarea Script y el componente de script permiten al desarrollador de software crear funcionalidad personalizada sin necesidad de escribir todo el código de infraestructura que se suele requerir al desarrollar una tarea personalizada o un componente de flujo de datos personalizado.  
  
## <a name="in-this-section"></a>En esta sección  
 [Comparación de la tarea Script y el componente de Script](../../integration-services/extending-packages-scripting/comparing-the-script-task-and-the-script-component.md)  
 Describe las similitudes y diferencias entre la tarea Script y el componente de script.  
  
 [Comparar soluciones de Scripting y objetos personalizados](../../integration-services/extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
 Describe los criterios que se deben utilizar al elegir entre una solución de scripting y el desarrollo de un objeto personalizado.  
  
 [Hacer referencia a otros ensamblados en soluciones de Scripting](../../integration-services/extending-packages-scripting/referencing-other-assemblies-in-scripting-solutions.md)  
 Describe los pasos necesarios para hacer referencia y utilizar ensamblados y espacios de nombres externos en un proyecto de scripting.  
  
 [Extender el paquete con la tarea de secuencia de comandos](../../integration-services/extending-packages-scripting/task/extending-the-package-with-the-script-task.md)  
 Describe cómo crear tareas personalizadas mediante la tarea Script. Normalmente, se llama a una tarea una vez por ejecución del paquete o una vez por cada origen de datos que abre un paquete.  
  
 [Extender el flujo de datos con el componente de Script](../../integration-services/extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md)  
 Explica cómo crear orígenes, transformaciones y destinos personalizados de flujo de datos mediante el componente de script. Normalmente se llama a un componente de flujo de datos una vez por cada fila de datos que se procesa.  
  
## <a name="reference"></a>Referencia  
 [Referencia de mensajes y Error de Integration Services](../../integration-services/integration-services-error-and-message-reference.md)  
 Muestra los códigos de error predefinidos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con sus nombres simbólicos y sus descripciones.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ampliar paquetes con objetos personalizados](../../integration-services/extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Explica cómo crear tareas personalizadas de programa, componentes de flujo de datos y otros objetos de paquete para su uso en varios paquetes.  
  
 [Generar paquetes mediante programación](../../integration-services/building-packages-programmatically/building-packages-programmatically.md)  
 Describe cómo crear, configurar, ejecutar, cargar, guardar y administrar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server Integration Services](../../integration-services/sql-server-integration-services.md)  
  
  