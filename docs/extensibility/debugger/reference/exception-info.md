---
title: EXCEPTION_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3ff28c46931905e3386a675711653fff99df8b08
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413584"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
Describe una excepción o error de tiempo de ejecución producido por el programa que se está depurando.

## <a name="syntax"></a>Sintaxis

```cpp
typedef struct tagEXCEPTION_INFO {
    IDebugProgram2* pProgram;
    BSTR            bstrProgramName;
    BSTR            bstrExceptionName;
    DWORD           dwCode;
    EXCEPTION_STATE dwState;
    GUID            guidType;
} EXCEPTION_INFO;
```

```csharp
public struct EXCEPTION_INFO {
    public IDebugProgram2 pProgram;
    public string         bstrProgramName;
    public string         bstrExceptionName;
    public uint           dwCode;
    public uint           dwState;
    public Guid           guidType;
};
```

## <a name="members"></a>Miembros
pProgram  
El [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objeto que representa el programa en el que se produjo la excepción.

bstrProgramName  
El nombre del programa en el que se produjo la excepción.

bstrExceptionName  
El nombre de la excepción.

dwCode  
El código de identificación del error de excepción o tiempo de ejecución.

dwState  
Un valor de la [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) enumeración que define el estado de la excepción.

guidType  
El identificador de idioma GUID, ya sea `guidLang` o `guidEng`.

## <a name="remarks"></a>Comentarios
Esta estructura se pasa como parámetro a la [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) y [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) métodos. Esta estructura también se pasa a la [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) método que deben rellenarse.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
[Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)  
[EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)  
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)  
[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)  
[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)  
[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)
