---
title: 'Cómo: editar archivos XML | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ac3864b3d3a3074f9b6be2529e8f674df90532c8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49245302"
---
# <a name="how-to-edit-xml-files"></a>Cómo: Editar archivos XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
El Editor XML es el nuevo editor de archivos XML. Se puede utilizar en un archivo XML independiente o en uno asociado con un proyecto de Visual Studio. El Editor XML está asociado con las siguientes extensiones de archivo: .config, .dtd, .xml, .xsd, .xdr, .xsl, .xslt y .vssettings. También está asociado con otros tipos de archivos que no tengan registrado un editor específico y que incluyan contenido XML o DTD.  
  
> [!NOTE]
>  Los documentos XHTML son manejados con el Editor HTML.  
  
### <a name="to-edit-an-xml-file"></a>Para editar un archivo XML  
  
1.  Haga doble clic en el archivo que desea editar.  
  
### <a name="to-add-a-new-xml-file-to-a-project"></a>Para agregar un nuevo archivo XML a un proyecto  
  
1.  Desde el **proyecto** menú, seleccione **Agregar nuevo elemento**.  
  
2.  Seleccione **archivo XML** desde el **plantillas** panel.  
  
3.  Escriba el nombre de archivo en el **nombre** campo y presione **agregar**.  
  
     Se agrega el archivo XML al proyecto y se abre en el Editor XML. El archivo contiene la declaración XML predeterminada, `<?xml version="1.0" encoding="utf-8" ?>`.  
  
### <a name="to-add-an-existing-xml-file-to-a-project"></a>Para agregar un archivo XML existente a un proyecto  
  
1.  Desde el **proyecto** menú, seleccione **Agregar elemento existente**.  
  
     El **Agregar elemento existente** aparece el cuadro de diálogo.  
  
2.  Seleccione un archivo XML y presione **agregar**.  
  
### <a name="to-create-a-new-xml-or-xslt-file"></a>Para crear un nuevo archivo XML o XSLT  
  
1.  Desde el **archivo** menú, seleccione **New**.  
  
     El **nuevo archivo** aparece el cuadro de diálogo.  
  
2.  Seleccione **archivo XML** para crear un nuevo archivo XML; o bien, seleccione **archivo XSLT** para crear una nueva hoja de estilos XSLT.  
  
3.  Haga clic en **abierto**.  
  
### <a name="to-create-a-project-for-xml-files"></a>Para crear un proyecto de archivos XML  
  
1.  Desde el **archivo** menú, seleccione **New**y, a continuación, seleccione **proyecto**.  
  
     Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione el lenguaje de código de su elección, seleccione **proyecto vacío**y haga clic en **Aceptar**.  
  
3.  Agregue archivos XML al proyecto.  
  
     El Editor XML busca los esquemas que agregue a este proyecto y los utiliza para la validación e IntelliSense en cualquier archivo XML, de esquema o XSLT que edite mientras este proyecto está abierto.  
  
## <a name="see-also"></a>Vea también  
 [Editor XML](../xml-tools/xml-editor.md)   
 [Propiedades del documento XML, ventana Propiedades](../xml-tools/xml-document-properties-properties-window.md)   
 [Cómo: Crear un esquema XML a partir de un documento XML](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)



