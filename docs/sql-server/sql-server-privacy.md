---
title: Complemento de privacidad de SQL Server | Microsoft Docs
ms.date: 4/24/2018
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.custom: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords: ''
helpviewer_keywords: ''
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 40c6bfb24ea3e711ca6b14509921d5599b316ebf
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "37975292"
---
# <a name="sql-server-privacy-supplement"></a>Complemento de privacidad de SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

En este artículo se resume el comportamiento de diferentes objetos de datos usados en SQL Server y cómo se usan dichos objetos para pasar información de manera personal o confidencial. Este artículo es un anexo a la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?LinkId=521839) general. La clasificación de datos de este artículo solo se aplica a versiones del producto local de SQL Server. No se aplica a los elementos:

- Base de datos SQL de Azure
- SQL Server Management Studio (SSMS)
- SQL Server Data Tools (SSDT)
- SQL Operations Studio
- Database Migration Assistant
- Asistente para migración de SQL Server
- Extensión MS-SQL

Definición de *escenarios de uso permitidos*. En el contexto de este artículo, Microsoft define los "escenarios de uso permitidos" como las acciones o las actividades que se inician a través de Microsoft.

## <a name="access-control"></a>Control de acceso

Información relacionada con las credenciales que se usa para proteger inicios de sesión, usuarios o cuentas en una instalación de SQL Server.

### <a name="examples-of-access-control"></a>Ejemplos de control de acceso

- Contraseñas
- Certificados

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos

|Escenario  |Restricciones de acceso               |Requisitos de retención |
|---------|---------|---------|
|Estas credenciales nunca salen del equipo del usuario con los comentarios de uso.     |-         |-         |
|Los volcados de memoria pueden contener datos de control de acceso.     |-         |Volcado de memoria: máximo 30 días.         |
|Estas credenciales nunca salen del equipo del usuario con los comentarios del usuario, a menos que el cliente las inserte manualmente.    |Limitado al uso interno de Microsoft sin acceso de terceros.         |Comentarios del usuario: máximo 1 año.         |
 |
## <a name="customer-content"></a>Contenido de cliente

El contenido de cliente se define como los datos almacenados en tablas de usuario, directa o indirectamente. Estos datos incluyen estadísticas o literales de usuario en los textos de consulta que pueden almacenarse en tablas de usuario.

### <a name="examples-of-customer-content"></a>Ejemplos de contenido de cliente

- Valores de datos almacenados en las filas de cualquier tabla de usuario.
- Objetos de estadísticas que contienen copias de valores en las filas de cualquier tabla de usuario.
- Textos de consulta que contienen valores literales.

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos
|Escenario  |Restricciones de acceso               |Requisitos de retención |
|---------|---------|---------|
|Estos dato no salen del equipo del usuario con los comentarios de uso. |- |- |
|Los volcados de memoria pueden incluir contenido de cliente y pueden emitirse para Microsoft. |- |Volcados de memoria: máximo 30 días. |
|Los clientes pueden enviar a Microsoft comentarios del usuario (con su consentimiento) que incluyan contenido de cliente. |Limitado al uso interno de Microsoft sin acceso de terceros. Microsoft puede exponer los datos al cliente original. |Comentarios del usuario: máximo 1 año. |

## <a name="end-user-identifiable-information-euii"></a>Información de identificación del usuario final (EUII)

Datos recibidos de un usuario o generados a partir de su uso del producto.
- Se pueden vincular a un usuario individual.
- No tienen contenido.

### <a name="examples-of-end-user-identifiable-information"></a>Ejemplos de información de identificación del usuario final

- Identificación de interfaces. La dirección IP completa
- Nombre del equipo
- Nombres de inicio de sesión o usuario
- Parte local de la dirección de correo electrónico (joe@contoso.com)
- Información de la ubicación
- Identificación del cliente

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos

|Escenario  |Restricciones de acceso               |Requisitos de retención|
|---------|---------|---------|
|Estos dato no salen del equipo del usuario con los comentarios de uso. |- |- |
|Los volcados de memoria pueden incluir EUII y pueden emitirse para Microsoft. |- |Volcados de memoria: máximo 30 días |
|Puede emitirse para Microsoft un identificador de cliente con el fin de ofrecer nuevas características híbridas y en la nube a las que se han suscrito los usuarios. |- |Actualmente no existe ninguna característica híbrida o en la nube de este tipo.|
|Los clientes pueden enviar a Microsoft comentarios del usuario (con su consentimiento) que incluyan contenido de cliente.|Limitado al uso interno de Microsoft sin acceso de terceros. Microsoft puede exponer los datos al cliente original. |Comentarios del usuario: máximo 1 año |

## <a name="internet-based-services-data"></a>Datos de servicios basados en Internet

Datos necesarios para ofrecer servicios basados en Internet, según los términos de licencia de SQL Server.

### <a name="examples-of-internet-based-services-data"></a>Ejemplos de datos de servicios basados en Internet

- Información sobre las especificaciones del equipo
- Nombre/versión del explorador
- Versión de SQL Server
- Código de lenguaje
- Una dirección IP con determinados octetos quitados
- Datos de mapa

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos

|Escenario  |Restricciones de acceso               |Requisitos de retención|
|---------|---------|---------| 
|Microsoft podría usarlos para mejorar las características y corregir errores de las características actuales. |Limitado al uso interno de Microsoft sin acceso de terceros. Microsoft puede exponer los datos al cliente original.  Por ejemplo, a través de paneles. |Mínimo 90 días, máximo 3 años. |
|Los clientes pueden enviar a Microsoft comentarios del usuario (con su consentimiento) que incluyan contenido de cliente. |Limitado al uso interno de Microsoft sin acceso de terceros. |Los clientes pueden enviar a Microsoft comentarios del usuario (con su consentimiento) que incluyan contenido de cliente. |
|Los elementos de mapa de Power View y SQL Reporting Services podrían enviar datos para el uso de Mapas de Bing. |Limitado a datos de la sesión. |- |

## <a name="system-metadata"></a>Metadatos del sistema

Datos generados durante el proceso de ejecución del servidor.  Los datos no incluyen contenido de cliente.

### <a name="examples-of-system-metadata"></a>Ejemplos de metadatos del sistema

La información siguiente se considera metadatos del sistema cuando no incluye contenido de cliente, control de acceso de cliente o EUII:

- GUID de base de datos
- Hash de nombre de equipo
- Hash de nombre de instancia
- Nombre de la aplicación
- Datos de uso y comportamiento
- Datos del Programa para la mejora de la experiencia del usuario de SQL (SQLCEIP)
- Datos de configuración del servidor, por ejemplo, las opciones de sp_configure
- Datos de configuración de características
- Nombres de eventos y códigos de error

Microsoft examina los valores de nombre de aplicación definidos por otros programas que usan SQL Server (por ejemplo, SharePoint o programas empaquetados de terceros) e incluye esta información en los metadatos de sistemas enviados a Microsoft cuando los datos de uso están habilitados. Los clientes no deben incluir datos personales, como información de identificación del usuario final, en campos de metadatos de sistemas ni crear aplicaciones diseñadas para almacenar datos personales en dichos campos. 

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos

|Escenario  |Restricciones de acceso  |Requisitos de retención|
|---------|---------|---------|
|Microsoft podría usarlos para mejorar las características y corregir errores de las características actuales.|Limitado al uso interno de Microsoft sin acceso de terceros. |Mínimo 90 días, máximo 3 años. |
|Pueden usarse para realizar sugerencias para el cliente.  Por ejemplo, "En función de su uso del producto, considere la posibilidad de usar la característica *X*, ya que obtendría mejores resultados". |Microsoft puede exponer los datos al cliente original, por ejemplo, a través de paneles. |Registros de seguridad de datos de cliente: mínimo 3 años, máximo 6 años. |
Microsoft podría usarlos para la planeación de productos en el futuro. |Microsoft puede compartir esta información con otros proveedores de hardware y software para mejorar el funcionamiento de sus productos con software de Microsoft. |Mínimo 90 días, máximo 3 años.|
|Microsoft podría usarlos para proporcionar servicios en la nube basados en los comentarios de uso emitidos. Por ejemplo, a través de un panel de cliente en el que se muestra el uso de características en todas las instalaciones de SQL Server de una organización. |Microsoft puede exponer los datos al cliente original, por ejemplo, a través de paneles. |Mínimo 90 días, máximo 3 años. |
|Los clientes pueden enviar a Microsoft comentarios del usuario (con su consentimiento) que incluyan contenido de cliente. |Limitado al uso interno de Microsoft sin acceso de terceros. Microsoft puede exponer los datos al cliente original. |Comentarios del usuario: máximo 1 año. |
|Puede usar el nombre de la base de datos y el de la aplicación para asignar categorías conocidas a las bases de datos y aplicaciones, por ejemplo, para las que pueden estar ejecutando software proporcionado por Microsoft u otras empresas.|Limitado al uso interno de Microsoft sin acceso de terceros.|Mínimo 90 días, máximo 3 años. |

## <a name="object-metadata"></a>Metadatos de objetos

Datos que describen servidores, bases de datos, tablas y otros recursos o que se usan para configurarlos.  Los metadatos de objetos incluyen la tabla de la base de datos y los nombres de columna, pero no el contenido de las filas de la base de datos u otro contenido de cliente. Los clientes no deben incluir datos personales, como información de identificación del usuario final, en campos de metadatos de objetos ni crear aplicaciones diseñadas para almacenar datos personales en dichos campos. En el caso de los escenarios de uso que se indican a continuación, solo se usa el formato de hash para determinar los patrones de uso con el fin de mejorar el producto. 

### <a name="examples-of-object-metadata"></a>Ejemplos de metadatos de objetos

- Nombres de bases de datos de SQL Server
- Nombres de tablas y columnas
- Nombres de estadísticas

### <a name="permitted-usage-scenarios"></a>Escenarios de uso permitidos

|Escenario  |Restricciones de acceso               |Requisitos de retención|
|---------|---------|---------|
|Microsoft podría usarlos para mejorar las características y corregir errores de las características actuales. |Limitado al uso interno de Microsoft sin acceso de terceros. |Mínimo 90 días, máximo 3 años.|

## <a name="telemetry-controls"></a>Controles de telemetría

Puede consultar las instrucciones sobre cómo activar o desactivar la telemetría en un producto en esta página: https://support.microsoft.com/en-us/help/3153756/how-to-configure-sql-server-2016-to-send-feedback-to-microsoft.

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]
