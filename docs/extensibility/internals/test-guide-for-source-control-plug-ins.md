---
title: Guía de pruebas para los complementos de Control de código fuente | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c7a1313a5d74f973e439d6177234eb11a202b344
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949693"
---
# <a name="test-guide-for-source-control-plug-ins"></a>Guía de pruebas para los complementos de control de código fuente
Esta sección proporciona instrucciones para probar su complemento con control de código fuente [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Se proporciona una visión general amplia de las áreas más comunes de pruebas, así como algunas de las áreas más complicadas que pueden ser problemáticas. Esta información general no pretende ser una lista exhaustiva de casos de prueba.  
  
> [!NOTE]
>  Algunas correcciones de errores y mejoras en la versión más reciente [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE puede revelar problemas con origen control complementos existentes que previamente no han encontrado durante el uso de las versiones anteriores de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Se recomienda encarecidamente que pruebe el control de código fuente existente complemento para las áreas que se enumeran en esta sección, incluso si no hay cambios realizados al complemento desde la versión anterior de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="common-preparation"></a>Preparación comunes  
 Una máquina con [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] y el complemento de control de código fuente de destino instalado, es necesario. Una segunda máquina configurada de forma similar puede utilizarse para algunas de la de apertura desde las pruebas de Control de código fuente.  
  
## <a name="definition-of-terms"></a>Definición de términos  
 Con el propósito de esta guía de prueba, use las siguientes definiciones de términos:  
  
 Proyecto de cliente  
 Cualquier proyecto de los tipos disponibles en [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] que admite la integración de control de código fuente (por ejemplo, [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], o [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]).  
  
 Proyecto Web  
 Hay cuatro tipos de proyectos Web: Sistema de archivos, IIS Local, sitios remotos y FTP.  
  
- Se crean proyectos de sistema de archivos en una ruta de acceso local, pero no requieren Internet Information Services (IIS) para instalarse cuando se tiene acceso internamente a través de una ruta de acceso UNC y pueden colocarse bajo control de código fuente desde el IDE, muy similar a los proyectos de cliente.  
  
- Proyectos IIS locales funcionan con IIS que está instalado en el mismo equipo y se tiene acceso con una dirección URL que apunta a la máquina local.  
  
- También se crean proyectos de sitios remotos en los servicios de IIS, pero están colocados bajo control de código fuente en el equipo del servidor IIS y no desde dentro de la [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
- Se tiene acceso a los proyectos FTP a través de un servidor FTP remoto pero no se puede colocar bajo control de código fuente.  
  
  Inscripción  
  Otro término de la solución o proyecto bajo control de código fuente.  
  
  Versión Store  
  La base de datos de control de código fuente que se accede a través de la API de complemento de Control de código fuente.  
  
## <a name="test-areas-covered-in-this-section"></a>En esta sección tratadas de áreas de pruebas  
  
-   [Área de prueba 1: Agregar a / abrir desde Control de código fuente](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    -   Case 1a: Agregar solución al Control de código fuente  
  
    -   Escenario 1b: Abrir solución desde el Control de código fuente  
  
    -   Caso 1C: Agregar solución desde Control de código fuente  
  
-   [Área de prueba 2: Obtener de Control de código fuente](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
-   [Área de prueba 3: Desproteger o deshacer desprotección](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    -   Caso 3: Desproteger o deshacer desprotección  
  
    -   Case 3a: Desproteger  
  
    -   Escenario 3b: Desprotección sin conexión  
  
    -   Caso 3C: Edición de consulta o consulta guardar (QEQS)  
  
    -   Caso 3d: Retirada silenciosa  
  
    -   Case 3e: Deshacer desprotección  
  
-   [Área de prueba 4: Check-in](../../extensibility/internals/test-area-4-check-in.md)  
  
    -   Escenario 4a: Elementos modificados  
  
    -   Escenario 4b: Agregar archivos  
  
    -   Caso 4 núcleos: Agregar proyectos  
  
-   [Área de prueba 5: Control de código fuente de cambios](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    -   Case 5a: Enlazar  
  
    -   Case 5b: Desenlazar  
  
    -   Mayúsculas y minúsculas 5c: volver a enlazar  
  
-   [Área de prueba 6: Delete](../../extensibility/internals/test-area-6-delete.md)  
  
-   [Área de prueba 7: Share](../../extensibility/internals/test-area-7-share.md)  
  
-   [Área de prueba 8: Cambio de complementos](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    -   Case 8a: Cambio automático  
  
    -   8b Case: Cambio de solución  
  
## <a name="see-also"></a>Vea también  
 [Complementos de control de código fuente](../../extensibility/source-control-plug-ins.md)