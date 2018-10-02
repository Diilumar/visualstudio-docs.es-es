---
title: Elemento (esquema del paquete de idioma VSIX) de la licencia | Documentos de Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57dac3b7-0cdd-405c-9af5-30ed9ca45e53
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ecf1913878137d84346275beccb512027f74f8f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47576707"
---
# <a name="license-element-vsix-language-pack-schema"></a>Elemento License (esquema del paquete de idioma VSIX)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [elemento License (esquema del paquete de idioma de VSIX)](https://docs.microsoft.com/visualstudio/extensibility/license-element-vsix-language-pack-schema).  
  
Opcional. La ruta de acceso de una versión localizada del archivo de licencia para la extensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<License>FilePath\license.txt</License>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|Ninguna||  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|Ninguna||  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento LanguagePack VSIX](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|Requerido. Proporciona el elemento raíz para un paquete de idioma VSIX.|  
  
## <a name="text-value"></a>Valor de texto  
 La ruta de acceso relativa del archivo de licencia localizados que se mostrará.  
  
## <a name="remarks"></a>Comentarios  
 Si el `License` elemento está definido, a continuación, se muestra el texto del archivo de licencia designada durante la instalación y el usuario debe aceptar la licencia para continuar.  
  
## <a name="element-information"></a>Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|Nombre de esquema|Esquema del paquete de idioma VSIX|  
|Archivo de validación|VSIXLanguagePackSchema.xsd|  
|Puede estar vacío|No es aplicable|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de esquema del paquete de idioma VSX](../extensibility/vsx-language-pack-schema-reference.md)   
 [Adaptación de paquetes VSIX](../extensibility/localizing-vsix-packages.md)   
 [Referencia de esquema 1.0 de extensión VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
