---
title: IDebugAddress2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 988e53c53b83658a2ca4338659a5f805f3bcf0e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47580068"
---
# <a name="idebugaddress2"></a>IDebugAddress2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [IDebugAddress2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugaddress2).  
  
Esta interfaz proporciona acceso al identificador de proceso que posee el objeto cuya dirección está representado por esta interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>Notas para los implementadores  
 Un proveedor de símbolos implementa esta interfaz en el mismo objeto que implementa el [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interfaz. Esta interfaz proporciona acceso al identificador de proceso que posee el objeto que está relacionado con esta dirección.  
  
## <a name="notes-for-callers"></a>Notas para los llamadores  
 Use [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) para obtener esta interfaz desde el [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interfaz.  
  
## <a name="methods-in-vtable-order"></a>Métodos en orden de vtable  
 Además de los métodos heredados de la [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interfaz, esta interfaz implementa el método siguiente:  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|Recupera el identificador de proceso que posee el objeto representado por esta interfaz.|  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de proveedor de símbolos](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
