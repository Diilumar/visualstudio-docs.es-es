---
title: Se necesita autorización de proxy | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b55dba438280fc4579fe15bd2a423d323c38abf6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767294"
---
# <a name="proxy-authorization-required"></a>Se necesita autorización de proxy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Por lo general, este error se produce cuando los usuarios están conectados a Visual Studio Online a través de un servidor proxy y el servidor proxy bloquea las llamadas. Visual Studio Online se usa para mantener la sesión del usuario iniciada en el IDE.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reinicie Visual Studio. Debe aparecer un cuadro de diálogo de autenticación de proxy. Escriba sus credenciales en el cuadro de diálogo.  
  
-   Si el paso anterior no resuelve el problema, puede que el servidor proxy no pida credenciales para direcciones http://go.microsoft.com, pero que sí lo haga para direcciones *.visualStudio.com. Para estos servidores, necesitará incluir en una lista blanca la siguiente lista para desbloquear todos los escenarios de inicio de sesión en Visual Studio:  
  
    -   *.windows.net  
  
    -   *.microsoftonline.com  
  
    -   *.visualstudio.com  
  
    -   *.microsoft.com  
  
    -   *.live.com  
  
-   En caso contrario puede quitar el http://go.microsoft.com de direcciones de la lista blanca para que el cuadro de diálogo de autenticación de proxy aparezca para ambas la http://go.microsoft.com dirección y los puntos de conexión de servidor cuando se reinicie Visual Studio.  
  
-   O  
  
-   Si desea usar las credenciales predeterminadas con el proxy, haga lo siguiente:  
  
    1.  Busque devenv.exe.config (el archivo de configuración de devenv.exe) en: **%Archivos de programa%\Microsoft Visual Studio 14.0\Common7\IDE** (o en **%Archivos de programa (x86)%\Microsoft Visual Studio 14.0\Common7\IDE**).  
  
    2.  En el archivo de configuración, busque el bloque `<system.net>` y agregue este código:  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         Debe insertar la dirección correcta del proxy de la red en `proxyaddress="<http://<yourproxy:port#>`.  
  
-   O  
  
-   También puede seguir las instrucciones de [esta publicación](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) para agregar código que le permitirá usar el proxy.
