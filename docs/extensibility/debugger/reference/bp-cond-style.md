---
title: BP_COND_STYLE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d8ca4f551f4dd6541bad9d73b5e91c671ad80492
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318308"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Especifica el estilo de condición de punto de interrupción para pendientes y puntos de interrupción enlazados.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
typedef DWORD BP_COND_STYLE;
```

```csharp
public enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
```

## <a name="members"></a>Miembros
BP_COND_NONE  
Se desencadena el punto de interrupción cuando se alcanza la posición del punto de interrupción. No se especifica ninguna condición de punto de interrupción.

BP_COND_WHEN_TRUE  
Se desencadena el punto de interrupción solo cuando la expresión condicional asociado con el punto de interrupción se evalúa como `true`.

BP_COND_WHEN_CHANGED  
Se desencadena el punto de interrupción solo cuando el valor de la expresión condicional asociado con el punto de interrupción se ha cambiado respecto a su evaluación anterior.

## <a name="remarks"></a>Comentarios
Utilizado para la `styleCondition` miembro de la [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) estructura.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
[Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
