---
title: 'Paso 4: Probar el paquete del tutorial de la lección 2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f9344531e59bd0b22ae99de4664c1433411b7f6e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48055985"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a>Paso 4: Probar el paquete del tutorial de la lección 2
  Con el contenedor de bucles Foreach y el administrador de conexiones de archivo plano que ha configurado, el paquete de la lección 2 puede iterarse a través de la colección de 14 archivos planos de la carpeta Datos de ejemplo. Cada vez que se encuentra un archivo que coincide con los criterios de nombre de archivo especificados, el contenedor de bucles Foreach rellena la variable definida por el usuario con el nombre de archivo. Esta variable, a su vez, actualiza la propiedad ConnectionString del administrador de conexiones de archivos planos, y se establece una conexión con el archivo plano nuevo. A continuación, el contenedor de bucles Foreach ejecuta la tarea de flujo de datos sin modificar en los datos del nuevo archivo plano antes de establecer conexión con el siguiente archivo de la carpeta.  
  
 Utilice el procedimiento siguiente para probar la nueva función del bucle que ha agregado al paquete.  
  
> [!NOTE]  
>  Si ejecutó el paquete desde la lección 1, necesitará eliminar los registros de dbo.FactCurrency en AdventureWorksDW2012 antes de ejecutar el paquete desde esta lección; de lo contrario, el paquete producirá errores que indican la infracción de una restricción de clave principal. Recibirá los mismos errores si ejecuta el paquete seleccionando Depurar/Iniciar la depuración (o presiona F5) porque se ejecutarán las lecciones 1 y 2. La lección 2 intentará insertar registros que ya se insertaron en la lección 1.  
  
## <a name="checking-the-package-layout"></a>Comprobar el diseño del paquete  
 Antes de probar el paquete, debe comprobar que los flujos de datos y de control de la lección 2 contienen los objetos mostrados en los diagramas siguientes. El flujo de datos debe ser idéntico al flujo de datos de la lección 1.  
  
 **Flujo de control**  
  
 ![Flujo de control del paquete](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")  
  
 **Flujo de datos**  
  
 ![Flujo de datos del paquete](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a>Para probar el paquete del tutorial de la lección 2  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Lesson 2.dtsx** y, después, haga clic en **Ejecutar paquete**.  
  
     El paquete se ejecutará. Puede comprobar el estado de cada bucle en la ventana Resultado o haciendo clic en la pestaña **Progreso** . Por ejemplo, puede ver que se han agregado 1.097 líneas a la tabla de destino del archivo Currency_VEB.txt.  
  
2.  Una vez que se haya completado la ejecución del paquete, en el menú **Depurar** , haga clic en **Detener depuración**.  
  
## <a name="next-lesson"></a>Lección siguiente  
 [Lección 5: Agregar configuraciones de paquete para el modelo de implementación de paquetes](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a>Vea también  
 [Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) (Ejecución de proyectos y paquetes)  
  
  
