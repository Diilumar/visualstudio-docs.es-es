---
title: '&lt;customErrorReporting&gt; elemento (implementación ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <customErrorReporting> element [ClickOnce deployment manifest]
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7254f5735be3efa45b7ba3be0541996cb6c2cc69
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997642"
---
# <a name="ltcustomerrorreportinggt-element-clickonce-deployment"></a>&lt;customErrorReporting&gt; elemento (implementación ClickOnce)
Especifica un URI que se va a mostrar cuando se produce un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<customErrorReporting  
   uri  
/>  
```  
  
## <a name="remarks"></a>Comentarios  
 Este elemento es opcional. Sin él, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] muestra un cuadro de diálogo que muestra la pila de excepciones. Si el `customErrorReporting` elemento está presente, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] en su lugar mostrará el URI indicado por el `uri` parámetro. El URI de destino incluirá la clase de excepción externa, la clase de excepción interna y el mensaje de excepción interna como parámetros.  
  
 Utilice este elemento para agregar funcionalidad a la aplicación de los informes de errores. Dado que el URI generado incluye información sobre el tipo de error, el sitio Web puede analizar esa información y mostrar, por ejemplo, una pantalla de la solución de problemas adecuada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente fragmento muestra el `customErrorReporting` elemento, junto con el URI generado que se podría producir.  
  
```xml
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />  
  
Example Generated Error:  
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.  
```  
  
## <a name="see-also"></a>Vea también  
 [Manifiesto de implementación de ClickOnce](../deployment/clickonce-deployment-manifest.md)