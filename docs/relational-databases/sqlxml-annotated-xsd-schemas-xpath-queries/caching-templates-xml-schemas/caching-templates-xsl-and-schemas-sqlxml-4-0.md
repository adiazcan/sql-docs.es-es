---
title: Almacenamiento en caché de plantillas, XSL y esquemas (SQLXML 4.0) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: b84ea32eea9e94818eae1331cbffd290b0c3bb39
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47670413"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a>Almacenar en memoria caché plantillas, XSL y esquemas (SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Para mejorar el rendimiento, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 permite almacenar en la memoria caché plantillas, archivos XSL y esquemas.  
  
 Todos los esquemas, plantillas y archivos XSL (excepto los archivos de una ubicación http:// o ftp://) están almacenados en la memoria caché. Los archivos almacenados en la memoria caché permanecen en memoria mientras el proceso se está ejecutando. Cuando finaliza el proceso, se pierde toda la caché. Por consiguiente, si ejecuta un proceso por consulta, es posible que no se aprecien las ventajas del almacenamiento en caché.  
  
 Los temas de esta sección proporcionan más información sobre cómo almacenar en memoria caché.  
  
## <a name="in-this-section"></a>En esta sección  
 [Almacenamiento en caché de plantilla &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/template-caching-sqlxml-4-0.md)  
 Se describe y proporciona una clave del Registro para el almacenamiento en caché de las plantillas.  
  
 [Almacenamiento en caché de XSL &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/xsl-caching-sqlxml-4-0.md)  
 Se describe y proporciona una clave del Registro para el almacenamiento en caché de archivos XSL.  
  
 [Almacenamiento en caché de esquema &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/schema-caching-sqlxml-4-0.md)  
 Se explican cuestiones de instalación simultánea de SQLXML relacionadas con el almacenamiento en la memoria caché de esquemas y proporciona las claves del Registro para el almacenamiento en caché de esquemas.  
  
  
