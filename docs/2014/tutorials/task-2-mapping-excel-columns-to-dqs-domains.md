---
title: 'Tarea 2: Asignar columnas de Excel a dominios de DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4af26cb52b8d30dbfad5fc5ab40dc732f8ce4dc2
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48135525"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a>Tarea 2: asignar columnas de Excel a dominios de DQS
    
1.  En la página **Asignación** , seleccione **Archivo de Excel** en **Origen de datos**.  
  
2.  Haga clic en **examinar**, seleccione **Suppliers.xlsx**y haga clic en **abierto**.  
  
3.  Seleccione **IncomingSuppliers$** para el **hoja de cálculo**.  
  
4.  Asigne las columnas como se muestra en la tabla y en la captura de pantalla siguientes. Al crear asignaciones para la **estado** dominio, haga clic en **agregar una asignación de columna** botón en la barra de herramientas se encuentra justo encima de la lista.  
  
    > [!TIP]  
    >  No usa **Id. de proveedor** dominio o de columna para la limpieza. Usará el **Id. de proveedor** dominio más adelante en la actividad de coincidencia.  
  
    |Columna de Excel|Dominio de DQS|  
    |------------------|----------------|  
    |Nombre de proveedor|Nombre de proveedor|  
    |ContactEmailAddress|Póngase en contacto con el correo electrónico|  
    |Address Line|Address Line|  
    |City|City|  
    |State|State|  
    |Country (haga clic en **+ (agregar una asignación de columna)** barra de herramientas para agregar una fila)|País|  
    |Zip Code|Zip|  
  
     ![Asignaciones de columnas de Excel a dominios](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "asignaciones de columnas de Excel a dominios")  
  
5.  Como ha asignado todos los dominios individuales dentro de la **validación de direcciones** dominio compuesto, el dominio compuesto automáticamente participa en el proceso de limpieza. Haga clic en **ver o seleccionar dominios compuestos** botón para ver que el **validación de direcciones** dominio compuesto se selecciona automáticamente y, a continuación, haga clic en **Aceptar**.  
  
     ![Cuadro de diálogo Ver o seleccionar dominios compuestos](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "cuadro de diálogo Ver o seleccionar dominios compuestos")  
  
6.  Haga clic en **siguiente** para cambiar a la **Cleanse** página.  
  
## <a name="next-step"></a>Paso siguiente  
 [Tarea 3: Limpiar datos con la base de conocimiento Proveedores](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
