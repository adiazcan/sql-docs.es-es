---
title: Ediciones y características admitidas de SQL Server 2017 | Microsoft Docs
ms.custom: ''
ms.date: 11/10/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Enterprise Edition [SQL Server]
- Developer Edition [SQL Server]
- 32-bit vs. 64-bit editions [SQL Server]
- default components
- Workgroup Edition [SQL Server]
- Internet servers [SQL Server]
- installing SQL Server, components
- Setup [SQL Server], components
- SQL Server, editions
- SQL Server, components
- client/server applications [SQL Server]
- editions [SQL Server]
- versions [SQL Server]
- Setup [SQL Server], editions
- SQL Server Installation Wizard
- components [SQL Server]
- Standard Edition [SQL Server]
- 64-bit edition [SQL Server]
- IIS [SQL Server]
- installing SQL Server, editions
- editions [SQL Server], about edition options
- Setup [SQL Server]
ms.assetid: ''
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: '>= sql-server-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: 3a21c80b335bd936eea957a7f9194dfa7040ad63
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47784953"
---
# <a name="editions-and-supported-features-of-sql-server-2017"></a>Ediciones y características admitidas de SQL Server 2017
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

En este tema se proporcionan detalles de las características compatibles con las diversas ediciones de SQL Server 2017. 

Para obtener información sobre versiones anteriores, consulte:

* [SQL Server 2016](editions-and-components-of-sql-server-2016.md).  
* [SQL Server 2014](http://msdn.microsoft.com/library/cc645993(v=sql.120).aspx).

  
Los requisitos de instalación varían según las necesidades de las aplicaciones. Las distintas ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] han sido diseñadas para satisfacer los requisitos de rendimiento, tiempo de ejecución y precio propios de cada organización y cada persona. Los componentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que instale también dependen de sus necesidades concretas. Las secciones siguientes le servirán de ayuda para elegir la mejor opción entre las ediciones y los componentes disponibles en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  

La edición de evaluación de SQL Server está disponible durante un período de prueba de 180 días.  
  
Para leer las notas de la versión más reciente e información sobre las novedades, vea lo siguiente:
- [Notas de la versión de SQL Server 2017](../sql-server/sql-server-2017-release-notes.md)
- [Novedades de SQL Server 2017](../sql-server/what-s-new-in-sql-server-2017.md)

### <a name="try-sql-server"></a>Pruebe SQL Server.    
    
> [![Descargar desde el Centro de evaluación](../analysis-services/media/download.png)](https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2017-ctp/) **[Descargar SQL Server 2017 desde el Centro de evaluación](https://www.microsoft.com/evalcenter/evaluate-sql-server-2017-ctp/)**    

<!---    
> ![Azure Virtual Machine small](../analysis-services/media/azure-virtual-machine-small.png) **[Spin up a Virtual Machine with SQL Server 2016 already installed](https://azuremarketplace.microsoft.com/marketplace/apps/Microsoft.SQL2016SP1-WS2016?tab=Overview?wt.mc_id=sqL16_vm)**   
--->

## <a name="includessnoversionincludesssnoversion-mdmd-editions"></a>Ediciones de[!INCLUDE[ssNoVersion](../includes/ssNoVersion-md.md)]   
 En la siguiente tabla se describen las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. 
  
|Edición de[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] |Definición|  
|---------------------------------------|----------------|  
|Enterprise|La mejor oferta, [!INCLUDE[ssNoVersion](../includes/ssNoVersion-md.md)] Enterprise Edition proporciona capacidades de centro de datos de tecnología avanzada completas con un rendimiento ultrarápido, virtualización ilimitada y Business Intelligence integral, que habilita los mayores niveles de servicio para las cargas de trabajo de gran importancia y el acceso del usuario final a ideas claras de los datos.|  
|Estándar|[!INCLUDE[ssNoVersion](../includes/ssNoVersion-md.md)] Standard Edition proporciona de administración básica de bases de datos y base de datos de Business Intelligence para que los departamentos y pequeñas organizaciones ejecuten sus aplicaciones y admite las herramientas de desarrollo comunes, tanto locales como en la nube, que habilitan la administración eficaz de bases de datos con recursos de TI mínimos.|  
|Web|[!INCLUDE[ssNoVersion](../includes/ssNoVersion-md.md)] Web Edition es una opción con un costo total de propiedad bajo para los hosts de Web y los VAP de Web que proporciona capacidades asequibles de administración y escalabilidad para propiedades web, tanto de pequeña como de gran escala.|  
|Desarrollador|[!INCLUDE[ssNoVersion](../includes/ssNoVersion-md.md)] Developer Edition permite a los desarrolladores compilar cualquier tipo de aplicación en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Incluye toda la funcionalidad de la edición Enterprise, pero tiene licencias para usarse como sistema de prueba y desarrollo, no como un servidor de producción. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Developer es una opción ideal para las personas que compilan y prueban aplicaciones.|  
|Ediciones Express|Express Edition es una base de datos gratuita para principiantes y es ideal para aprender a compilar pequeñas aplicaciones de servidor y de escritorio orientadas a datos. Es la mejor opción para los fabricantes de software independientes, los desarrolladores y los aficionados que compilan aplicaciones cliente. Si necesita características de base de datos más avanzadas, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express se puede actualizar sin problemas a otras versiones superiores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express LocalDB es una versión ligera de Express que tiene todas sus características de capacidad de programación, se ejecuta en modo usuario y presenta una instalación rápida y sin configuración, y una lista reducida de requisitos previos.|  
  
## <a name="using-includessnoversionincludesssnoversion-mdmd-with-an-internet-server"></a>Usar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con un servidor de Internet  
 En un servidor de Internet, como el servidor en el que se ejecuta Internet Information Services (IIS), se instalan normalmente las herramientas de cliente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . Las herramientas de cliente incluyen los componentes de conectividad del cliente utilizados por una aplicación que se conecta a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
>[!NOTE]
>Aunque puede instalar una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en un equipo en el que se ejecute IIS, esto suele hacerse únicamente para sitios web pequeños que tienen un único equipo servidor. La mayoría de los sitios web tienen los sistemas IIS de capa intermedia en un servidor o un clúster de servidores, y las bases de datos en un servidor o federación de servidores independientes.  
  
## <a name="using-includessnoversionincludesssnoversion-mdmd-with-clientserver-applications"></a>Uso de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con aplicaciones cliente/servidor  
 Puede instalar solo los componentes de cliente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en un equipo en el que se ejecuten aplicaciones cliente/servidor conectadas directamente a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Una instalación de componentes de cliente también es una buena opción si administra una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en un servidor de bases de datos, o si tiene pensado desarrollar aplicaciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .  
  
 La opción de herramientas cliente instala las características siguientes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] : componentes de compatibilidad con versiones anteriores, herramientas de datos de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], componentes de conectividad, herramientas de administración, kit de desarrollo de software y componentes de los Libros en pantalla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . Para obtener más información, consulte [Instalar SQL Server](../database-engine/install-windows/install-sql-server.md).  
  
## <a name="deciding-among-includessnoversionincludesssnoversion-mdmd-components"></a>Decisión entre componentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
 Use la página Selección de características del Asistente para la instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para seleccionar los componentes que va a incluir en la instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. De forma predeterminada, ninguna de las características del árbol están seleccionadas.  
  
 Use la información de las tablas siguientes para determinar el conjunto de características que mejor satisface sus necesidades.  
  
|Componentes de servidor|Descripción|  
|-----------------------|-----------------|  
|[!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]|[!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] incluye el [!INCLUDE[ssDE](../includes/ssde-md.md)], el servicio principal para almacenar, procesar y proteger datos; también incluye replicación, búsqueda de texto completo, herramientas para administrar datos XML y relacionales, integración de análisis en base de datos e integración de PolyBase para el acceso a Hadoop y a otros orígenes de datos heterogéneos, además del servidor de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).|  
|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] incluye las herramientas para crear y administrar aplicaciones de procesamiento analítico en línea (OLAP) y de minería de datos.|  
|[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]|[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] incluye componentes de servidor y de cliente para crear, administrar e implementar informes tabulares, matriciales, gráficos y de forma libre. [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] es también una plataforma extensible que se puede usar para desarrollar aplicaciones de informes.|  
|[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]|[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] es un conjunto de herramientas gráficas y objetos programables para mover, copiar y transformar datos. También incluye el componente de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) para [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].|  
|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS) es la solución de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para la administración de datos maestros. MDS se pueden configurar para administrar cualquier dominio (productos, clientes, cuentas) e incluye jerarquías, seguridad específica, transacciones, creación de versiones de datos y reglas de negocios, así como un [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] que se puede usar para administrar datos.|  
|Machine Learning Services (en base de datos)|Machine Learning Services (en base de datos) admite soluciones de aprendizaje automático distribuidas y escalables con orígenes de datos empresariales. En SQL Server 2016, se admitía el lenguaje R. SQL Server 2017 admite R y Python.|
|Machine Learning Server (independiente)|Machine Learning Server (independiente) admite la implementación de soluciones de aprendizaje automático distribuidas y escalables en varias plataformas y con varios orígenes de datos empresariales, incluidos Linux y Hadoop. En SQL Server 2016, se admitía el lenguaje R. SQL Server 2017 admite R y Python.|

  
|Herramientas de administración|Descripción|  
|----------------------|-----------------|  
|[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]|[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] es un entorno integrado para obtener acceso a los componentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]y configurarlos, administrarlos y desarrollarlos. [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] permite a los desarrolladores de software y a los administradores de diversos grados de conocimientos utilizar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].<br /><br /> Descargue e instale <br />                [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] desde  [Descargar SQL Server Management Studio](http://msdn.microsoft.com/library/mt238290.aspx)|  
|Administrador de configuración de[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] |El Administrador de configuración de[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] proporciona administración de configuración básica para los servicios, protocolos de servidor, protocolos de cliente y alias de cliente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .|  
|[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]|[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] proporciona una interfaz gráfica de usuario para supervisar una instancia del [!INCLUDE[ssDE](../includes/ssde-md.md)] o de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].|  
|Asistente para la optimización de[!INCLUDE[ssDE](../includes/ssde-md.md)] |El Asistente para la optimización de[!INCLUDE[ssDE](../includes/ssde-md.md)] crea conjuntos óptimos de índices, vistas indizadas y particiones.|  
|Cliente de calidad de datos|Proporciona una interfaz gráfica de usuario muy simple y intuitiva para conectarse al servidor de DQS y realizar operaciones de limpieza de datos. También permite supervisar de forma centralizada diversas actividades realizadas durante la operación de limpieza de datos.|  
|[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]|[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] proporciona un IDE para compilar soluciones para los componentes de Business Intelligence: [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]y [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].<br /><br /> (Anteriormente denominado Business Intelligence Development Studio).<br /><br /> [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] SSDT también incluye "Proyectos de base de datos", que proporcionan un entorno integrado para que los desarrolladores de software de bases de datos realicen todo el trabajo de diseño de base de datos para cualquier plataforma de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (tanto interna como externa) en Visual Studio. Los desarrolladores de software de base de datos pueden usar el Explorador de servidores mejorado en Visual Studio para crear o modificar objetos de base de datos y datos fácilmente, o bien para ejecutar consultas.|  
|Componentes de conectividad|Instala componentes para la comunicación entre clientes y servidores, y bibliotecas de red para DB-Library, ODBC y OLE DB.|  
  
|Documentación|Descripción|  
|-------------------|-----------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Libros en pantalla|Documentación principal para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].| 

**Ediciones Developer y Evaluation**  
Para obtener las características compatibles con las ediciones Developer y Evaluation, vea las características enumeradas para SQL Server Enterprise Edition en las tablas siguientes.

La edición Developer sigue siendo compatible con solo un cliente de [SQL Server Distributed Replay](../tools/distributed-replay/sql-server-distributed-replay.md). 
  
##  <a name="Cross-BoxScaleLimits"></a> Límites de escala  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express| 
|-------------|----------------|--------------|---------|------------------------------------|------------------------|
|Capacidad máxima de cálculo que usa una sola instancia: [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]<sup>1</sup>|Sistema operativo máximo|Limitada a menos de 4 sockets o 24 núcleos|Limitada a menos de 4 sockets o 16 núcleos|Limitada a menos de 1 socket o 4 núcleos|Limitada a menos de 1 socket o 4 núcleos| 
|Capacidad máxima de cálculo que usa una sola instancia: [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]|Sistema operativo máximo|Limitada a menos de 4 sockets o 24 núcleos|Limitada a menos de 4 sockets o 16 núcleos|Limitada a menos de 1 socket o 4 núcleos|Limitada a menos de 1 socket o 4 núcleos|  
|Memoria máxima para el grupo de búferes por cada instancia de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]|Sistema operativo máximo|128 GB|64 GB|1410 MB|1410 MB|
|Cantidad máxima de memoria para la caché de segmento del almacén de columnas por cada instancia de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]|Memoria ilimitada| 32 GB| 16 GB| 352 MB| 352 MB|  
|Tamaño máximo de datos optimizados para memoria por base de datos en [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]|Memoria ilimitada| 32 GB| 16 GB| 352 MB| 352 MB|  
|Memoria máxima usada por instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]|Sistema operativo máximo|Tabular: 16 GB<br /><br /> MOLAP: 64 GB|N/D|N/D|N/D|  
|Memoria máxima usada por instancia de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]|Sistema operativo máximo|64 GB|64 GB|4 GB|N/D|
|Tamaño máximo de la base de datos relacional|524 PB|524 PB|524 PB|10 GB|10 GB|  
  
<sup>1</sup> La licencia basada en Enterprise Edition con licencia de servidor y acceso de cliente (CAL) (no disponible para nuevos contratos) está limitada a un máximo de 20 núcleos por instancia de SQL Server. No hay ningún límite en el modelo de licencias de servidor basado en núcleos. Para obtener más información, consulte [Compute Capacity Limits by Edition of SQL Server](../sql-server/compute-capacity-limits-by-edition-of-sql-server.md).  
 
##  <a name="RDBMSHA"></a> Alta disponibilidad de RDBMS  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------|  
|Compatibilidad con Server Core <sup>1</sup>|Sí|Sí|Sí|Sí|Sí|  
|Trasvase de registros|Sí|Sí|Sí|no|no|  
|Creación de reflejo de base de datos|Sí|Sí<br /><br /> Solo seguridad completa|Solo testigo|Solo testigo|Solo testigo| 
|Compresión de copia de seguridad|Sí|Sí|no|no|no| 
|Instantáneas de base de datos|Sí|Sí|Sí|Sí|Sí|
|Instancias de clúster de conmutación por error de AlwaysOn<sup>2</sup>|Sí|Sí|no|no|no|  
|Grupos de disponibilidad AlwaysOn<sup>3</sup>|Sí|no|no|no|no|
|Grupos de disponibilidad básica<sup>4</sup>|no|Sí|no|no|no|
|Restauración de archivos y páginas en línea|Sí|no|no|no|no|
|Índices en línea|Sí|no|no|no|no|
|Recompilaciones de índices en línea reanudables|Sí|no|no|no|no|
|Cambio de esquema en línea|Sí|no|no|no|no|
|Recuperación rápida|Sí|no|no|no|no|
|Copias de seguridad reflejadas|Sí|no|no|no|no|
|Agregar memoria y CPU sin interrupción|Sí|no|no|no|no|
|Asistente para la recuperación de base de datos|Sí|Sí|Sí|Sí|Sí|
|Copia de seguridad cifrada|Sí|Sí|no|no|no|
|Copia de seguridad híbrida en Windows Azure (copia de seguridad en dirección URL)|Sí|Sí|no|no|no|
|Grupo de disponibilidad sin clúster|Sí|Sí|no|no|no|no|
|Grupo de disponibilidad de confirmación de réplica mínima|Sí|Sí|Sí|no|no|no|
  

<sup>1</sup> Para obtener más información sobre cómo instalar SQL Server en Server Core, vea [Instalar SQL Server en Server Core](../database-engine/install-windows/install-sql-server-on-server-core.md). 

<sup>2</sup> En Enterprise Edition, el número de nodos es el sistema operativo máximo. En Standard Edition hay compatibilidad con dos nodos. 

<sup>3</sup> En Enterprise Edition, proporciona compatibilidad con hasta 8 réplicas secundarias, incluidas 2 réplicas secundarias sincrónicas. 

<sup>4</sup> Standard Edition admite grupos de disponibilidad básica. Un grupo de disponibilidad básica admite dos réplicas, con una base de datos. Para más información sobre los grupos de disponibilidad básica, vea [Grupos de disponibilidad básica](../database-engine/availability-groups/windows/basic-availability-groups-always-on-availability-groups.md).  


##  <a name="RDBMSSP"></a> Escalabilidad y rendimiento de RDBMS  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------| 
|Almacén de columnas <sup>1</sup>|Sí|Sí|Sí|Sí|Sí|  
|Archivos binarios de objetos de gran tamaño en índices de almacén de columnas en clúster|Sí|Sí|Sí|Sí|Sí|  
|Recompilación de índices de almacén de columnas no en clúster en línea|Sí|no|no|no|no|
|OLTP en memoria <sup>1</sup>|Sí|Sí|Sí|Sí, <sup>2</sup>|Sí|
|Stretch Database|Sí|Sí|Sí|Sí|Sí|
|Memoria principal persistente|Sí|Sí|Sí|Sí|Sí|
|Compatibilidad con varias instancias|50|50|50|50|50|
|Particiones de tabla e índice|Sí|Sí|Sí|Sí|Sí|  
|Compresión de datos|Sí|Sí|Sí|Sí|Sí|
|Regulador de recursos|Sí|no|no|no|no|  
|Paralelismo de tabla con particiones|Sí|no|no|no|no|
|Varios contenedores de secuencias de archivo|Sí|Sí|Sí|Sí|Sí|
|Asignación de memoria de página grande habilitada para NUMA y matriz de búferes|Sí|no|no|no|no|
|Buffer Pool Extension|Sí|Sí|no|no|no|
|Regulación de recursos de E/S|Sí|no|no|no|no|  
|Perdurabilidad diferida|Sí|Sí|Sí|Sí|Sí|
|Ajuste automático|Sí|no|no|no|no|
|Combinaciones adaptables de modo de proceso por lotes|Sí|no|no|no|no|
|Comentarios de concesión de memoria de modo de proceso por lotes|Sí|no|no|no|no|
|Ejecución intercalada de funciones con valores de tabla de múltiples instrucciones|Sí|Sí|Sí|Sí|Sí|
|Mejoras de inserción masiva|Sí|Sí|Sí|Sí|Sí|


<sup>1</sup> El tamaño de los datos de OLTP en memoria y la memoria caché del segmento del almacén de columnas se limitan a la cantidad de memoria especificada por edición en la sección Límites de escala. Los grados de paralelismo máximos están limitados. Los grados de paralelismo (DOP) para la compilación de un índice se limitan a 2 DOP para Standard Edition y 1 DOP para las ediciones Web y Express. Se refiere a los índices de almacén de columnas que se crean en tablas basadas en disco y en tablas optimizadas para memoria.

<sup>2</sup> Esta característica no está incluida en la opción de instalación LocalDB.

##  <a name="RDBMSS"></a> Seguridad de RDBMS  
  
|Característica|Enterprise|Estándar|Web|Express|Express con Advanced Services|  
|-------------|----------------|--------------|---------|-------------|------------------------------------| 
|Seguridad de nivel de fila|Sí|Sí|Sí|Sí|Sí|  
|Always Encrypted|Sí|Sí|Sí|Sí|Sí| 
|Enmascaramiento de datos dinámicos|Sí|Sí|Sí|Sí|Sí|   
|Auditoría básica|Sí|Sí|Sí|Sí|Sí| 
|Auditoría específica|Sí|Sí|Sí|Sí|Sí| 
|Cifrado de base de datos transparente|Sí|no|no|no|no|   
|Administración extensible de claves|Sí|no|no|no|no| 
|Roles definidos por el usuario|Sí|Sí|Sí|Sí|Sí| 
|Bases de datos independientes|Sí|Sí|Sí|Sí|Sí| 
|Cifrado para copias de seguridad|Sí|Sí|no|no|no|  

##  <a name="Replication"></a> Replication  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|   
|-------------|----------------|--------------|---------|------------------------------------|------------------------| 
|Suscriptores heterogéneos|Sí|Sí|no|no|no|  
|Replicación de mezcla|Sí|Sí|Sí (solo suscriptor)|Sí (solo suscriptor)|Sí (solo suscriptor)|   
|Publicación de Oracle|Sí|no|no|no|no| 
|Replicación transaccional punto a punto|Sí|no|no|no|no|   
|Replicación de instantáneas|Sí|Sí|Sí (solo suscriptor)|Sí (solo suscriptor)|Sí (solo suscriptor)|   
|Seguimiento de cambios de SQL Server|Sí|Sí|Sí|Sí|Sí| 
|Replicación transaccional|Sí|Sí|Sí (solo suscriptor)|Sí (solo suscriptor)|Sí (solo suscriptor)|   
|Replicación transaccional a Azure|Sí|Sí|no|no|no|   
|Suscripción actualizable a la replicación transaccional|Sí|no|no|no|no|  
  
##  <a name="SSMS"></a> Herramientas de administración  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express| 
|-------------|----------------|--------------|---------|------------------------------------|------------------------|  
|Objetos de administración de SQL (SMO)|Sí|Sí|Sí|Sí|Sí|  
|Administrador de configuración de SQL|Sí|Sí|Sí|Sí|Sí|   
|SQL CMD (herramienta del símbolo del sistema)|Sí|Sí|Sí|Sí|Sí|      
|Distributed Replay: herramienta de administración|Sí|Sí|Sí|Sí|no|  
|Distribute Replay: cliente|Sí|Sí|Sí|no|no|  
|Distributed Replay: controlador|Sí (hasta 16 clientes)|Sí (1 cliente)|Sí (1 cliente)|no|no|   
|SQL Profiler|Sí|Sí|No <sup>1</sup>|No <sup>1</sup>|No <sup>1</sup>|  
|Agente SQL Server|Sí|Sí|Sí|no|no| 
|Paquete de administración de Microsoft System Center Operations Manager|Sí|Sí|Sí|no|no|  
|Asistente para la optimización de motor de base de datos (DTA)|Sí|Sí <sup>2</sup>|Sí <sup>2</sup>|no|no|      
  
 <sup>1</sup> Se pueden generar perfiles de SQL Server Web, SQL Server Express, SQL Server Express con herramientas y SQL Server Express con Advanced Services mediante las ediciones SQL Server Standard y SQL Server Enterprise.  
  
 <sup>2</sup> La optimización se habilita solo en las características de la edición Standard  
  
##  <a name="RDBMSM"></a> Capacidad de administración de RDBMS  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|   
|-------------|----------------|--------------|---------|------------------------------------|------------------------|  
|Instancias de usuario|no|no|no|Sí|Sí| 
|LocalDB|no|no|no|Sí|no| 
|Conexión de administración dedicada|Sí|Sí|Sí|Sí, con marca de seguimiento|Sí, con marca de seguimiento|   
|Compatibilidad con SysPrep <sup>1</sup>|Sí|Sí|Sí|Sí|Sí| 
|Compatibilidad con scripting de PowerShell<sup>2</sup>|Sí|Sí|Sí|Sí|Sí| 
|Compatibilidad con las operaciones de componentes de aplicación de capa de datos: extracción, implementación, actualización, eliminación|Sí|Sí|Sí|Sí|Sí| 
|Automatización de directivas (comprobar en la programación y cambio)|Sí|Sí|Sí|no|no|   
|Recopilador de datos de rendimiento|Sí|Sí|Sí|no|no| 
|Capacidad de inscribirse como instancia administrada en una administración de varias instancias|Sí|Sí|Sí|no|no|   
|Informes de rendimiento estándar|Sí|Sí|Sí|no|no| 
|Guías del plan y congelación del plan para las guías del plan|Sí|Sí|Sí|no|no|   
|Consulta directa de vistas indexadas (mediante la sugerencia NOEXPAND)|Sí|Sí|Sí|Sí|Sí| 
|Mantenimiento automático de vistas indexadas|Sí|Sí|Sí|no|no| 
|Vistas distribuidas con particiones|Sí|no|no|no|no| 
|Operaciones indizadas en paralelo|Sí|no|no|no|no|  
|Uso automático de vistas indexadas por el optimizador de consultas|Sí|no|no|no|no| 
|Comprobación de coherencia en paralelo|Sí|no|no|no|no| 
|Punto de control de la utilidad de SQL Server|Sí|no|no|no|no|    
|Extensión del grupo de búferes|Sí|Sí|no|no|no| 
  
 <sup>1</sup> Para más información, vea [Consideraciones acerca de la instalación de SQL Server con SysPrep](../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md).  
 
 <sup>2</sup> En Linux, se admiten los scripts de PowerShell, desde equipos de Windows que se dirigen a los servidores de SQL Server en Linux. 
##  <a name="DevTools"></a> Herramientas de desarrollo  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express| 
|-------------|----------------|--------------|---------|------------------------------------|------------------------| 
|Integración de Microsoft Visual Studio|Sí|Sí|Sí|Sí|Sí| 
|IntelliSense (Transact-SQL y MDX)|Sí|Sí|Sí|Sí|Sí| 
|SQL Server Data Tools (SSDT)|Sí|Sí|Sí|Sí|no|    
|Herramientas de edición, depuración y diseño de MDX|Sí|Sí|no|no|no|   
  
##  <a name="Programmability"></a> Programmability  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express 
|-------------|----------------|--------------|---------|------------------------------------|------------------------|  
|Integración básica de R <sup>1</sup>|Sí|Sí|Sí|Sí|no|   
|Integración avanzada de R <sup>2</sup>|Sí|no|no|no|no| 
|Integración básica de Python|Sí|Sí|Sí|Sí|no|
|Integración avanzada de Python|Sí|no|no|no|no| 
|Machine Learning Server (independiente)|Sí|no|no|no|no|   
|Nodo de ejecución de Polybase|Sí|Sí <sup>3</sup>|Sí <sup>3</sup>|Sí <sup>3</sup>|Sí <sup>3</sup> | 
|Nodo principal de Polybase|Sí|no|no|no|no| 
|JSON|Sí|Sí|Sí|Sí|Sí|   
|Almacén de consultas|Sí|Sí|Sí|Sí|Sí|   
|Temporal|Sí|Sí|Sí|Sí|Sí|   
|Integración de Common Language Runtime (CLR)|Sí|Sí|Sí|Sí|Sí|   
|Compatibilidad con XML nativo|Sí|Sí|Sí|Sí|Sí| 
|Índices XML|Sí|Sí|Sí|Sí|Sí| 
|Funciones MERGE y UPSERT|Sí|Sí|Sí|Sí|Sí|   
|compatibilidad con FILESTREAM|Sí|Sí|Sí|Sí|Sí| 
|FileTable|Sí|Sí|Sí|Sí|Sí| 
|Tipos de datos de fecha y hora|Sí|Sí|Sí|Sí|Sí|  
|Compatibilidad para internacionalización|Sí|Sí|Sí|Sí|Sí| 
|Búsqueda de texto completo y semántica|Sí|Sí|Sí|Sí|no| 
|Especificación de idioma en la consulta|Sí|Sí|Sí|Sí|no|   
|Service Broker (mensajería)|Sí|Sí|No (solo cliente)|No (solo cliente)|No (solo cliente)|   
|Transact-SQL, extremos|Sí|Sí|Sí|no|no| 
|Gráfico|Sí|Sí|Sí|Sí|Sí|  


<sup>1</sup> La integración básica se limita a dos núcleos y conjuntos de datos en memoria. 

<sup>2</sup> La integración avanzada puede usar todos los núcleos disponibles para el procesamiento paralelo de conjuntos de datos de cualquier tamaño sujeto a las limitaciones del hardware. 

<sup>3</sup> El escalado horizontal con varios nodos de cálculo exige un nodo principal.


## <a name="IS"></a> Integration Services

Para obtener información sobre las características de SQL Server Integration Services (SSIS) compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], vea [Características de Integration Services compatibles con las ediciones de SQL Server](../integration-services/integration-services-features-supported-by-the-editions-of-sql-server.md).

##  <a name="MDS"></a> Master Data Services  
 Para obtener información sobre las características de [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] y Data Quality Services compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Master Data Services y Data Quality Services compatibles con las ediciones de SQL Server](../master-data-services/master-data-services-and-data-quality-services-features-support.md). 

  
##  <a name="DW"></a> Almacenamiento de datos  
  
|Característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|   
|-------------|----------------|--------------|---------|------------------------------------|------------------------| 
|Crear cubos sin base de datos|Sí|Sí|no|no|no |   
|Ensayo de generación automática y esquema de almacenamiento de datos|Sí|Sí|no|no|no| 
|captura de datos modificados|Sí|Sí|no|no|no| 
|Optimizaciones de consultas de combinación en estrella|Sí|no|no|no|no| 
|Configuración de solo lectura escalable de Analysis Services|Sí|no|no|no|no| 
|Procesamiento de consultas en paralelo en las tablas e índices con particiones|Sí|no|no|no|no|   
|Agregación global de lotes|Sí|no|no|no|no| 

##  <a name="SSAS"></a> Analysis Services  
  
Para obtener información sobre las características de Analysis Services compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md). 
  
##  <a name="BIMD"></a> Modelo semántico BI (multidimensional)  
  
Para obtener información sobre las características de Analysis Services compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md).
   
##  <a name="BIT"></a> Modelo semántico BI (tabular)  
  
Para obtener información sobre las características de Analysis Services compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md).
  
##  <a name="PPSP"></a> Power Pivot for SharePoint  
  
Para obtener información sobre las características de Power Pivot para SharePoint compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md).
  
##  <a name="DM"></a> Minería de datos  
  
Para obtener información sobre las características de minería de datos compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md).
  
##  <a name="SSRS"></a> Reporting Services  
  
Para obtener información sobre las características de Reporting Services compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Reporting Services compatibles con las ediciones de SQL Server](../reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016.md).

##  <a name="BIC"></a> Clientes de inteligencia empresarial  

Para obtener información sobre las características de Business Intelligence Client compatibles con las ediciones de [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)], consulte [Características de Analysis Services compatibles con las ediciones de SQL Server](../analysis-services/analysis-services-features-supported-by-the-editions-of-sql-server-2016.md) o [Características de Reporting Services compatibles con las ediciones de SQL Server](../reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016.md).
  
##  <a name="SLS"></a> Servicios espaciales y de ubicación  
  
|Nombre de la característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|  
|------------------|----------------|--------------|---------|------------------------------------|------------------------|
|Índices espaciales|Sí|Sí|Sí|Sí|Sí|   
|Tipos de datos planares y geodésicos|Sí|Sí|Sí|Sí|Sí| 
|Bibliotecas espaciales avanzadas|Sí|Sí|Sí|Sí|Sí|   
|Importación y exportación de formatos de datos espaciales estándar del sector|Sí|Sí|Sí|Sí|Sí|   
  
##  <a name="ADS"></a> Servicios de bases de datos adicionales  
  
|Nombre de la característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|   
|------------------|----------------|--------------|---------|------------------------------------|------------------------| 
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Migration Assistant|Sí|Sí|Sí|Sí|Sí|   
|Correo electrónico de base de datos|Sí|Sí|Sí|no|no| 
  
##  <a name="Other"></a> Otros componentes  
  
|Nombre de la característica|Enterprise|Estándar|Web|Express con Advanced Services|Express|   
|------------------|----------------|--------------|---------|------------------------------------|------------------------|  
|StreamInsight|StreamInsight Premium Edition|StreamInsight Standard Edition|StreamInsight Standard Edition|no|no| 
|StreamInsight HA|StreamInsight Premium Edition|no|no|no|no|   

> [![Descargar SSMS](../analysis-services/media/download.png)](../ssms/download-sql-server-management-studio-ssms.md)Descargar la versión más reciente de **[SQL Server Management Studio](../ssms/download-sql-server-management-studio-ssms.md)**     
  
## <a name="next-steps"></a>Pasos siguientes 
 [Especificaciones de producto para SQL Server](http://msdn.microsoft.com/library/6445fd53-6844-4170-a86b-7fe76a9f64cb)   
 [Instalación de SQL Server](../database-engine/install-windows/installation-for-sql-server-2016.md)  
 
[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]

[!INCLUDE[contribute-to-content](../includes/paragraph-content/contribute-to-content.md)]
