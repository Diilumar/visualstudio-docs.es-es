---
title: "Extraer método - refactorización (C#) | Documentos de Microsoft"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: csharp
ms.openlocfilehash: 3890d427ed2888647675a241f4e62a5635d7308c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2017
---
# <a name="extract-a-method-in-c"></a>Extraer un método en C# #
**¿Qué:** le permite convertir un fragmento de código en su propio método.

**Cuándo:** tiene un fragmento de código existente en algún método que debe llamarse desde otro método.  

**Por este motivo:** se puede copiar y pegar ese código, pero esto conduciría a la duplicación.  Una mejor solución consiste en refactorizar ese fragmento en su propio método que se puede llamar libremente con cualquier otro método.

**Cómo:**

1. Resalte el código que se va a extraer:

   ![Código que aparece resaltado](media/extractmethod_highlight.png)

1. A continuación, realice una de las siguientes acciones:
   * **Teclado**
     * Presione **Ctrl + R**, a continuación, **Ctrl + M**.  (Tenga en cuenta que su método abreviado de teclado puede ser diferente en función del perfil que haya seleccionado).
     * Presione **Ctrl +.** Para activar el **acciones rápidas y refactorizaciones** menú y seleccione **Extraer método** desde la ventana emergente de ventana de vista previa.
   * **Mouse**
     * Seleccione **Editar > refactorizar > Extraer método**.
     * Haga clic en el código y seleccione **refactorizar > Extraer > Extraer método**.
     * Haga clic en el código, seleccione la **acciones rápidas y refactorizaciones** menú y seleccione **Extraer método** desde la ventana emergente de ventana de vista previa.

   Se creará inmediatamente el método.  Desde aquí, ahora puede cambiar el nombre del método, simplemente escribiendo el nuevo nombre.

   > [!TIP]
   > También puede actualizar los comentarios y otras cadenas para usar este nuevo nombre, así como [obtener una vista previa de cambios](../../ide/preview-changes.md) antes de guardar, mediante las casillas de verificación en la **cambiar el nombre de** cuadro que aparece en la parte superior derecha de su IDE.

   ![Cambiar el nombre de método](media/extractmethod_rename.png)

1. Cuando esté satisfecho con el cambio, haga clic en el **aplicar** o presionen **ENTRAR** y los cambios se confirmarán.

## <a name="see-also"></a>Vea también  
[Refactorización (C#)](../refactoring-csharp.md)  
[Vista previa de cambios](../../ide/preview-changes.md)