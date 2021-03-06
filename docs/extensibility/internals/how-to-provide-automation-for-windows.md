---
title: Procedimiento Provisión de automatización para Windows | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4a4482069d16ef6f0f64472b838057949890a6d3
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335160"
---
# <a name="how-to-provide-automation-for-windows"></a>Filtrar Provisión de automatización para windows

Puede proporcionar automatización para ventanas de herramientas y documentos. Proporcionar automatización es aconsejable cada vez que se desea disponer de los objetos de automatización en una ventana, y el entorno no proporciona un objeto de automatización listos para su uso, ya que lo hace con una lista de tareas.

## <a name="automation-for-tool-windows"></a>Automatización de las ventanas de herramientas

El entorno proporciona automatización en una ventana de herramientas devolviendo un estándar <xref:EnvDTE.Window> objeto tal como se explica en el procedimiento siguiente:

1.  Llame a la <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> método a través del entorno con [__VSFPROPID. VSFPROPID_ExtWindowObject](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_ExtWindowObject>) como `VSFPROPID` para obtener el `Window` objeto.

2.  Cuando un llamador solicita un objeto de automatización específico de VSPackage de la ventana de herramientas a través de <xref:EnvDTE.Window.Object%2A>, el entorno llama a `QueryInterface` para `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, o el `IDispatch` interfaces. Ambos `IExtensibleObject` y `IVsExtensibleObject` proporcionan un <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> método.

3.  Cuando el entorno, a continuación, llama a la `GetAutomationObject` método pasando `NULL`, realizar una copia de responder al pasar el objeto específico de VSPackage.

4.  Si una llamada a `QueryInterface` para `IExtensibleObject` y `IVsExtensibleObject` produce un error, el entorno llama a `QueryInterface` para `IDispatch`.

## <a name="automation-for-document-windows"></a>Automatización de las ventanas de documento

Un estándar <xref:EnvDTE.Document> objeto también está disponible desde el entorno, aunque un editor puede tener su propia implementación de la <xref:EnvDTE.Document> objeto implementando `IExtensibleObject` interfaz y responder a `GetAutomationObject`.

Además, un editor puede proporcionar un objeto de automatización específico de VSPackage, recuperado a través de la <xref:EnvDTE.Document.Object%2A> método implementando la `IVsExtensibleObject` o `IExtensibleObject` interfaces. El [muestras de VSSDK](http://aka.ms/vs2015sdksamples) contribuye a un objeto de automatización específicos del documento RTF.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>