---
title: "JsGetOwnPropertyDescriptor (Funci&#243;n) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetOwnPropertyDescriptor"
helpviewer_keywords: 
  - "JsGetOwnPropertyDescriptor (función)"
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# JsGetOwnPropertyDescriptor (Funci&#243;n)
Obtiene un descriptor de propiedad para la propia propiedad de un objeto.  
  
## Sintaxis  
  
```  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### Parámetros  
 `object`  
 El objeto que tiene la propiedad.  
  
 `propertyId`  
 El identificador de la propiedad.  
  
 `propertyDescriptor`  
 El descriptor de la propiedad.  
  
## Valor devuelto  
 El código `JsNoError` si la operación se realizó correctamente; en caso contrario, un código de error.  
  
## Comentarios  
 Requiere un contexto de script activo.  
  
## Requisitos  
 **Encabezado:** jsrt.h  
  
## Vea también  
 [Referencia \(Runtime de JavaScript\)](../chakra-hosting/reference-javascript-runtime.md)