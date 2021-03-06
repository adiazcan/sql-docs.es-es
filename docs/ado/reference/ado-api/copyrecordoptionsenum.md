---
title: CopyRecordOptionsEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CopyRecordOptionsEnum
helpviewer_keywords:
- CopyRecordOptionsEnum enumeration [ADO]
ms.assetid: 2fa4eec5-d50b-4fd3-8ae7-40af441ba12b
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: fe0b12053b9ac7203253e81fa3300d2e4109a129
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47681572"
---
# <a name="copyrecordoptionsenum"></a>CopyRecordOptionsEnum
Especifica el comportamiento de la [CopyRecord](../../../ado/reference/ado-api/copyrecord-method-ado.md) método.  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adCopyAllowEmulation**|4|Indica que el *origen* proveedor intenta simular la copia mediante la descarga y cargar operaciones si este método produce un error debido a *destino*está en un servidor diferente o es atendido por otro proveedor que *origen*. Tenga en cuenta que diferentes capacidades de proveedor pueden afectar al rendimiento o pérdida de datos.|  
|**adCopyNonRecursive**|2|Copia el directorio actual, pero ninguno de sus subdirectorios, en el destino. La operación de copia no es recursiva.|  
|**adCopyOverWrite**|1|Si se sobrescribe el archivo o directorio el *destino* apunta a un archivo o directorio existente.|  
|**adCopyUnspecified**|-1|Predeterminado: Realiza la operación de copia de forma predeterminada: la operación produce un error si el archivo de destino o directorio ya existe y la copia de operación de forma recursiva.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO y WFC  
 Estas constantes no tienen equivalentes de ADO y WFC.  
  
## <a name="applies-to"></a>Se aplica a  
 [Método CopyRecord (ADO)](../../../ado/reference/ado-api/copyrecord-method-ado.md)
