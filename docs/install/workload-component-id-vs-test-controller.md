---
title: Identificadores de componente y carga de trabajo de Visual Studio Test Controller 2017
titleSuffix: ''
description: Uso de identificadores de componente y carga de trabajo de Visual Studio para distribuir pruebas automatizadas en varias máquinas
keywords: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 11/13/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.assetid: fbbda9c8-d2c6-474d-b52d-a95227d52fe7
ms.workload:
- multiple
ms.openlocfilehash: b115e1433de72891cf6d01bfb326e93ea81971d2
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911811"
---
# <a name="visual-studio-test-controller-2017-component-directory"></a>Directorio de componentes de Visual Studio Test Controller 2017

Las tablas de esta página presentan los identificadores que puede usar para instalar Visual Studio mediante la línea de comandos o que puede especificar como una dependencia en un manifiesto VSIX. Tenga en cuenta que agregaremos componentes adicionales a medida que se publiquen actualizaciones de Visual Studio.

Tenga en cuenta también lo siguiente sobre la página:

* Cada carga de trabajo tiene su propia sección, seguida por el identificador de la carga de trabajo y una tabla de los componentes que están disponibles para la carga de trabajo.
* De forma predeterminada, los componentes con carácter **Obligatorio** se instalarán cuando se instala la carga de trabajo.
* Si lo desea, también puede instalar los componentes con la marca **Recomendado** y **Opcional**.
* También hemos agregado una sección que muestra los componentes adicionales que no están asociados a ninguna carga de trabajo.

Al establecer las dependencias del manifiesto de VSIX, debe especificar solo identificadores de componentes. Utilice las tablas de esta página para determinar las dependencias de componente mínimas. En algunos casos, esto podría significar que se especifique solo un componente de una carga de trabajo. En otros escenarios, puede significar que especifique varios componentes de una sola carga de trabajo o varios componentes de varias cargas de trabajo. Para obtener más información, vea la página [Cómo: Migrar proyectos de extensibilidad a Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

Para obtener más información acerca de cómo utilizar estos identificadores, vea [Usar parámetros de la línea de comandos para instalar Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md). Y, para obtener una lista de los identificadores de componente y carga de trabajo para otros productos, consulte la página [Visual Studio 2017 Workload and Component IDs](workload-and-component-ids.md) (Identificadores de componente y carga de trabajo de Visual Studio 2017).

## <a name="test-controller"></a>Test Controller

**ID:** Microsoft.VisualStudio.Workload.TestController

**Descripción:** Distribuye las pruebas automatizadas en varias máquinas

### <a name="components-included-by-this-workload"></a>Componentes incluidos en esta carga de trabajo

Id. de componente | nombre | Versión | Tipo de dependencia
--- | --- | --- | ---
Microsoft.VisualStudio.ComponentGroup.TestTools.TestController | Características principales de Test Controller | 15.6.27309.0 | Obligatorio

## <a name="unaffiliated-components"></a>Componentes no afiliados

Estos son componentes que no están incluidos en ninguna carga de trabajo, pero que pueden seleccionarse como un componente individual.

Id. de componente | nombre | Versión
--- | --- | ---
N/D | N/D | N/D

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Vea también

* [Identificadores de cargas de trabajo y componentes de Visual Studio](workload-and-component-ids.md)
* [Guía del administrador de Visual Studio](visual-studio-administrator-guide.md)
* [Usar parámetros de la línea de comandos para instalar Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
  * [Ejemplos de parámetros de línea de comandos](command-line-parameter-examples.md)
* [Crear una instalación sin conexión de Visual Studio](create-an-offline-installation-of-visual-studio.md)
