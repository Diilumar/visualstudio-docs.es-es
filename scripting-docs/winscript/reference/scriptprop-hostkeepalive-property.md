---
title: SCRIPTPROP_HOSTKEEPALIVE (propiedad) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: bfa199f2-28ba-4320-bc0f-2320fad018bd
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c8918e277fa9c7183e6d46a4853824a74fa4548
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346844"
---
# <a name="scriptprophostkeepalive-property"></a>SCRIPTPROP_HOSTKEEPALIVE (Propiedad)
Se utiliza para especificar si el motor de scripting se debe mantener totalmente funcional si hay referencias pendientes.  
  
 Use [IActiveScriptProperty::SetProperty](../../winscript/reference/iactivescriptproperty-setproperty.md) para establecer esta propiedad en `true`. Si esta propiedad se establece en `true`, se mantiene el motor de scripting totalmente funcional, siempre hay al menos una referencia pendiente para el motor de scripting o a un `IDispatch` puntero a un objeto de JavaScript creado mediante el uso de las secuencias de comandos motor. Cuando esta propiedad se establece en `true`, explícitamente no debe cerrar o restablecer el motor de scripts mediante el [IActiveScript::Close](../../winscript/reference/iactivescript-close.md) o [IActiveScript:: Setscriptstate](../../winscript/reference/iactivescript-setscriptstate.md) métodos. La versión de la última referencia a un objeto de script cierra el motor de scripts.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
#define SCRIPTPROP_HOSTKEEPALIVE 0x70000004  
```  
  
## <a name="requirements"></a>Requisitos  
 Esta propiedad solo aparece en la versión de activscp.idl que se instala con [!INCLUDE[win8](../../javascript/includes/win8-md.md)], con 2707082 KB para Internet Explorer 8 en [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)], o con 2722913 KB para Internet Explorer 9 en [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)] o [!INCLUDE[vista_first](../../winscript/reference/includes/vista-first-md.md)].