---
title: 'Paso 6: Los cambios se envían al servidor (Tutorial de RDS) | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], changes sent to server
ms.assetid: b1e927d6-7d50-4978-9eef-045043cdce7a
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2d79fb88ba9371d1767561c7190818c135fd0a03
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47680273"
---
# <a name="step-6-changes-are-sent-to-the-server-rds-tutorial"></a>Paso 6: los cambios se envían al servidor (Tutorial de RDS)
Si el **Recordset** se edita el objeto, los cambios (es decir, las filas que se agregan, cambian o eliminan) pueden enviarse al servidor.  
  
> [!NOTE]
>  El comportamiento predeterminado de RDS se puede invocar implícitamente con objetos ADO y el proveedor de servicios remotos de Microsoft OLE DB. Las consultas pueden devolver **Recordset**s y editado **Recordset**s puede actualizar el origen de datos. En este tutorial no utiliza RDS con objetos ADO, pero se trata de cómo sería si lo hiciera:  
  
```  
Dim rs as New ADODB.Recordset  
rs. "SELECT * FROM Authors","=MS Remote;=Pubs;" & _  
=http://yourServer;=SQLOLEDB;"  
...              ' Edit the Recordset.  
rs.   ' The equivalent of   
...  
```  
  
 **Parte A** suponga para este caso de que solo haya usado el [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) y que un **Recordset** objeto está ahora asociado el **RDS. DataControl**. El [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md) método actualiza el origen de datos con los cambios realizados en el **Recordset** objeto si el [Server](../../../ado/reference/rds-api/server-property-rds.md) y [Connect](../../../ado/reference/rds-api/connect-property-rds.md) todavía se establecen las propiedades.  
  
```  
Sub RDSTutorial6A()  
Dim DC as New RDS.DataControl  
Dim RS as ADODB.Recordset  
DC. = "http://yourServer"  
DC. = "DSN=Pubs"  
DC. = "SELECT * FROM Authors"  
DC.  
...  
Set RS = DC.  
   ' Edit the Recordset.  
...  
DC.  
...  
```  
  
 **La parte B** como alternativa, podría actualizar el servidor con el [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) objeto, especificando una conexión y un **Recordset** objeto.  
  
```  
Sub RDSTutorial6B()  
Dim DS As New RDS.DataSpace  
Dim RS As ADODB.Recordset  
Dim DC As New RDS.DataControl  
Dim DF As Object  
Dim blnStatus As Boolean  
Set DF = DS.("RDSServer.DataFactory", "http://yourServer")  
Set RS = DF. ("DSN=Pubs", "SELECT * FROM Authors")  
DC. = RS    ' Visual controls can now bind to DC.  
    ' Edit the Recordset.  
blnStatus = DF."DSN=Pubs", RS  
End Sub  
```  
  
 **Éste es el final del tutorial.**  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, componentes de servidor RDS ya no están incluidos en el sistema operativo de Windows (consulte Windows 8 y [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) para obtener más detalles). Componentes de cliente RDS se quitará en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Deben migrar las aplicaciones que usan RDS a [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>Vea también  
 [Proveedor de servicios remotos de Microsoft OLE DB (proveedor de servicios de ADO)](../../../ado/guide/appendixes/microsoft-ole-db-remoting-provider-ado-service-provider.md)   
 [Tutorial de RDS](../../../ado/guide/remote-data-service/rds-tutorial.md)   
 [Tutorial de RDS (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
