---
title: Idialinenumber | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_length method
ms.assetid: 2c55a6f7-4ef5-45fb-9fd1-d72deaaa2829
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c2e30106b5f410e57f6dacd5cc2d91d88928588
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47582062"
---
# <a name="idialinenumbergetlength"></a>IDiaLineNumber::get_length
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [Idialinenumber](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialinenumber-get-length).  
  
Recupera el número de bytes en un bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT get_length (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pRetVal`  
 [out] Devuelve el número de bytes en un bloque.  
  
## <a name="return-value"></a>Valor devuelto  
 Si es correcto, devuelve `S_OK`. Devuelve `S_FALSE` si no se admite esta propiedad. De lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 El bloque es la longitud del código fuente en la línea representada por el [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md) objeto.  
  
## <a name="see-also"></a>Vea también  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)


