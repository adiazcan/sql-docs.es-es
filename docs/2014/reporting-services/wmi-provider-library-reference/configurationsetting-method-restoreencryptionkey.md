---
title: Método RestoreEncryptionKey (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
api_name:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: baf827dbedeb8a822a729e27d08fca4fa6b7f95a
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48172095"
---
# <a name="restoreencryptionkey-method-wmi-msreportserverconfigurationsetting"></a>Método RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting)
  Vuelve a aplicar la clave de cifrado especificada a la base de datos del servidor de informes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>Parámetros  
 *KeyFile[]*  
 [out] Matriz que contiene la clave de cifrado cifrada.  
  
 *Longitud*  
 [out] Longitud de la matriz devuelta por el método.  
  
 *Contraseña*  
 Una cadena utilizada para cifrar la clave de cifrado.  
  
 *HRESULT*  
 [out] Valor que indica si la llamada se realizó correctamente o no.  
  
 *ExtendedErrors[]*  
 [out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no. Un valor de 0 indica que la llamada al método se realizó correctamente. Un valor distinto de cero indica que se ha producido un error.  
  
## <a name="remarks"></a>Comentarios  
 Si ya existe una entrada para el servidor de informes en la base de datos del servidor de informes, se elimina. A continuación, se crea la nueva entrada utilizando la clave de cifrado especificada y la clave pública del servidor de informes.  
  
 El método es más efectivo cuando se llama después de la [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) método, que borra la lista de las claves de cifrado.  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Miembros MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
