---
title: Método SetDefaults (clase CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: b242e76bb714088895048cb869473c23d2e4cb07
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48080865"
---
# <a name="setdefaults-method-cinstance-class"></a>Método SetDefaults (clase CInstance)
  Establece todos los valores predeterminados para la instancia de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente con la opción para sobrescribir los datos existentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Objeto de la [clase CInstance](cinstance-class.md) que representa una instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|*OverwriteAll*|Valor booleano que especifica si se van a sobrescribir los valores existentes en la instancia del cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `true` para sobrescribir los datos existentes o `false` para no sobrescribirlos.|  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="see-also"></a>Vea también  
 [Configurar protocolos de cliente](http://technet.microsoft.com/library/ms181035.aspx)  
  
  
