---
title: Establecer las propiedades | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ceffa7d590ad7861b07700ac13ab795a309bff39
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48080995"
---
# <a name="setting-properties"></a>Establecer propiedades
  Las propiedades son valores que almacenan información descriptiva sobre el objeto. Por ejemplo, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] las opciones de configuración se representan mediante el <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> propiedades del objeto. Se puede tener acceso a las propiedades de forma directa o indirecta mediante la colección de propiedades. Para tener acceso directamente a las propiedades, se utiliza la sintaxis siguiente:  
  
 `objInstance.PropertyName`  
  
 Un valor de propiedad se puede modificar o recuperar dependiendo de si la propiedad tiene acceso de lectura/escritura o acceso de solo lectura. También es necesario establecer ciertas propiedades antes de que se pueda crear un objeto. Para obtener más información, vea la referencia de SMO del objeto concreto.  
  
> [!NOTE]  
>  Las colecciones de objetos secundarios aparecen como la propiedad de un objeto. Por ejemplo, el `Tables` colección es una propiedad de un `Server` objeto. Para obtener más información, consulte [usar colecciones](using-collections.md).  
  
 Las propiedades de un objeto son miembros de la colección Properties. La colección Properties se puede utilizar para recorrer en iteración cada propiedad de un objeto.  
  
 A veces una propiedad no está disponible por las razones siguientes:  
  
-   La versión de servidor no admite la propiedad, como en el caso de que intente obtener acceso a una propiedad que representa una nueva característica de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en una versión anterior de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
-   El servidor no proporciona datos para la propiedad, por ejemplo, si intenta tener acceso a una propiedad que representa un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] componente que no está instalado.  
  
 Puede controlar estas circunstancias si detecta las excepciones SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> y <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.  
  
## <a name="setting-default-initialization-fields"></a>Establecer campos de inicialización predeterminados  
 SMO realiza una optimización al recuperar objetos. La optimización reduce el número de propiedades cargadas mediante la aplicación de una escala automática entre los estados siguientes:  
  
1.  Parcialmente cargado. Cuando se hace referencia por primera vez a un objeto, tiene un mínimo de propiedades disponibles (como Nombre y Esquema).  
  
2.  Totalmente cargado. Cuando se hace referencia a una propiedad, las propiedades restantes que se cargan rápidamente se inicializan y pasan a estar disponibles.  
  
3.  Propiedades que utilizan mucha memoria. Las propiedades no disponibles restantes utilizan mucha memoria y tienen un <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> valor de propiedad es True (como <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>). Estas propiedades solo se cargan cuando se hace referencia a ellas de forma específica.  
  
 Si la aplicación captura propiedades adicionales, además de las que se proporcionan en el estado parcialmente cargado, envía una consulta para recuperar estas propiedades adicionales y pasa al estado totalmente cargado. Esto puede producir un tráfico innecesario entre cliente y servidor. Mayor optimización puede lograrse mediante una llamada a la <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> método. El método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> permite la especificación de las propiedades que se cargan al inicializar el objeto.  
  
 El método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> establece el comportamiento de carga de propiedades para el resto de aplicación o hasta que se restablece. Puede guardar el comportamiento original mediante el <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> método y restaurarlo cuando sea necesario.  
  
## <a name="examples"></a>Ejemplos  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a>Obtener y establecer una propiedad en Visual Basic  
 Este ejemplo de código muestra cómo obtener el <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Information> objeto y cómo establecer el <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> propiedad a la `ExecuteSql` miembro de la <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> tipo enumerado.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a>Obtener y establecer una propiedad en Visual C#  
 Este ejemplo de código muestra cómo obtener el <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Information> objeto y cómo establecer el <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> propiedad a la `ExecuteSql` miembro de la <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> tipo enumerado.  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a>Establecer diversas propiedades antes de crear un objeto en Visual Basic  
 Este ejemplo de código muestra cómo establecer directamente la <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Table> objeto y cómo crear y agregar columnas antes de crear el <xref:Microsoft.SqlServer.Management.Smo.Table> objeto.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a>Establecer diversas propiedades antes de crear un objeto en Visual C#  
 Este ejemplo de código muestra cómo establecer directamente la <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Table> objeto y cómo crear y agregar columnas antes de crear el <xref:Microsoft.SqlServer.Management.Smo.Table> objeto.  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a>Recorrer en iteración todas las propiedades de un objeto en Visual Basic  
 Este ejemplo de código se recorre el `Properties` colección del <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> objeto y los muestra en el [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pantalla de salida.  
  
 En el ejemplo, el <xref:Microsoft.SqlServer.Management.Smo.Property> objeto se ha incluido entre corchetes porque también es un [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] palabra clave.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a>Recorrer en iteración todas las propiedades de un objeto en Visual C#  
 Este ejemplo de código se recorre el `Properties` colección del <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> objeto y los muestra en el [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pantalla de salida.  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a>Establecer campos de inicialización predeterminados en Visual Basic  
 En este ejemplo de código se muestra cómo minimizar el número de propiedades de objeto inicializadas en un programa SMO. Debe incluir el `using System.Collections.Specialized`; instrucción que se utiliza el <xref:System.Collections.Specialized.StringCollection> objeto.  
  
 Puede utilizarse [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] para comparar el número de instrucciones enviadas a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con esta optimización.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a>Establecer campos de inicialización predeterminados en Visual C#  
 En este ejemplo de código se muestra cómo minimizar el número de propiedades de objeto inicializadas en un programa SMO. Debe incluir el `using System.Collections.Specialized`; instrucción que se utiliza el <xref:System.Collections.Specialized.StringCollection> objeto.  
  
 Puede utilizarse [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] para comparar el número de instrucciones enviadas a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con esta optimización.  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
