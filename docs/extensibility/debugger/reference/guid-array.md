---
title: GUID_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c3aa33d8cef230d07c9b5f7cd3bd11a538fa651a
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315526"
---
# <a name="guidarray"></a>GUID_ARRAY
Describe una matriz de identificadores únicos para los motores de depuración disponible.

## <a name="syntax"></a>Sintaxis

```cpp
typedef struct tagGUID_ARRAY
{
    DWORD dwCount;
    GUID *Members;
} GUID_ARRAY;
```

```csharp
public struct GUID_ARRAY
{
    public uint dwCount;
    public Guid Members;
}
```

## <a name="terms"></a>Términos
dwCount  
Número de identificadores únicos de la matriz.

Miembros  
Matriz que contiene identificadores únicos.

## <a name="remarks"></a>Comentarios
Esta estructura es devuelto por la [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) método.

## <a name="requirements"></a>Requisitos
Encabezado: Msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
[Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)
