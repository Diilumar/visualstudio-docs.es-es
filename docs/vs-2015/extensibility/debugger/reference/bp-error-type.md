---
title: BP_ERROR_TYPE | Microsoft Docs
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
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 574830c7875b0711d6e14aa5b09370a5bf217903
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47578833"
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [BP_ERROR_TYPE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-error-type).  
  
Especifica el tipo de error de un punto de interrupción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```csharp  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## <a name="members"></a>Miembros  
 BPET_NONE  
 No especifica que ningún error de punto de interrupción.  
  
 BPET_TYPE_WARNING  
 Especifica un error de punto de interrupción de advertencia de estilo.  
  
 BPET_TYPE_ERROR  
 Especifica un error de punto de interrupción de estilo de error.  
  
 BPET_SEV_HIGH  
 Especifica un punto de interrupción de alta gravedad de error.  
  
 BPET_SEV_GENERAL  
 Especifica un punto de interrupción de gravedad de error.  
  
 BPET_SEV_LOW  
 Especifica un error de punto de interrupción de gravedad baja.  
  
 BPET_TYPE_MASK  
 Especifica un error de punto de interrupción de estilo de máscara.  
  
 BPET_SEV_MASK  
 Especifica un punto de interrupción de estilo de máscara de gravedad de error.  
  
 BPET_GENERAL_WARNING  
 Especifica un error de punto de interrupción de estilo de advertencia general.  
  
 BPET_GENERAL_ERROR  
 Especifica un error de punto de interrupción de estilo de error general.  
  
 BPET_ALL  
 Especifica todos los tipos de error de punto de interrupción.  
  
## <a name="remarks"></a>Comentarios  
 Estos valores se pueden combinar con un bit a bit `OR` y se utiliza para la `dwType` miembro de la [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) estructura. Pasado como parámetro a la [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) método.  
  
 Un tipo de error de punto de interrupción se compone de un tipo y un nivel de gravedad. Esto significa que un tipo de error de punto de interrupción nunca es simplemente un tipo (por ejemplo, `BPET_TYPE_ERROR`,) o un nivel de gravedad (por ejemplo, `BPET_SEV_GENERAL`) por sí mismo. `BPET_GENERAL_WARNING` y `BPET_GENERAL_ERROR` proporcionar valores predefinidos para puntos de interrupción de advertencia y error generales.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
