---
title: BP_STATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95e228a3aa0e96eedcf0413df7680e7a5664b707
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315422"
---
# <a name="bpstate"></a>BP_STATE
Especifica la existencia de un punto de interrupción enlazado y también especifica si está habilitado.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
typedef DWORD BP_STATE;
```

```csharp
public enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>Miembros
BPS_NONE  
Especifica que no existe ningún punto de interrupción.

BPS_DELETED  
Especifica que se ha eliminado el punto de interrupción.

BPS_DISABLED  
Especifica que el punto de interrupción está deshabilitado.

BPS_ENABLED  
Especifica que el punto de interrupción está habilitado.

## <a name="remarks"></a>Comentarios
Devuelve el [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) método.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
[Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)
