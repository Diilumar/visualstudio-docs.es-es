---
title: "C&#243;mo: ampliar rangos en documentos mediante programaci&#243;n"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "rangos, extender"
  - "documentos [desarrollo de Office en Visual Studio], extender rangos"
ms.assetid: 055af7a4-13d5-4236-b5fb-a112721482c5
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# C&#243;mo: ampliar rangos en documentos mediante programaci&#243;n
  Después de definir un objeto <xref:Microsoft.Office.Interop.Word.Range> en un documento de Microsoft Office Word, se pueden cambiar sus puntos de inicio y final mediante los métodos <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> y <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A>. Los métodos <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> y <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> usan los mismos argumentos, *Unit* y *Count*. El argumento *Count* es el número de unidades que se mueven y el argumento *Unit* puede ser uno de los siguientes valores <xref:Microsoft.Office.Interop.Word.WdUnits>:  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCharacter>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdWord>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSentence>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdParagraph>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSection>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdStory>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCell>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdColumn>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdRow>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdTable>  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 En el ejemplo siguiente se define un rango de siete caracteres. A continuación, se mueve la posición inicial del rango siete caracteres después de la posición inicial original. Puesto que la posición final del rango también estaba situada siete caracteres después de la posición inicial, el resultado es un rango que consta de cero caracteres. Posteriormente, el código mueve la posición final siete caracteres después de la posición final actual.  
  
### Para extender un rango  
  
1.  Defina un rango de caracteres. Para obtener más información, consulte [Cómo: Definir y seleccionar intervalos en documentos mediante programación](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md).  
  
     El siguiente ejemplo de código se puede usar en una personalización de nivel de documento.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#39](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#39)]
     [!code-vb[Trin_VstcoreWordAutomation#39](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#39)]  
  
     El siguiente ejemplo de código se puede usar en un complemento de VSTO. En este ejemplo se usa el documento activo.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#39](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#39)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#39](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#39)]  
  
2.  Use el método <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> del objeto <xref:Microsoft.Office.Interop.Word.Range> para mover la posición inicial del rango.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#40](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#40)]
     [!code-vb[Trin_VstcoreWordAutomation#40](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#40)]  
  
3.  Use el método <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> del objeto <xref:Microsoft.Office.Interop.Word.Range> para mover la posición final del rango.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#41](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#41)]
     [!code-vb[Trin_VstcoreWordAutomation#41](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#41)]  
  
## Código de personalizaciones de nivel de documento  
  
#### Para extender un rango en una personalización de nivel de documento  
  
1.  En el siguiente ejemplo se muestra el código completo de una personalización de nivel de documento. Para usar este código, ejecútelo desde la clase `ThisDocument` del proyecto.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#38](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#38)]
     [!code-vb[Trin_VstcoreWordAutomation#38](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#38)]  
  
## Código de complementos de VSTO  
  
#### Para extender un rango en un complemento de VSTO de nivel de aplicación  
  
1.  En el siguiente ejemplo se muestra el código completo de un complemento de VSTO. Para usar este código, ejecútelo desde la clase `ThisAddIn` del proyecto.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#38](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#38)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#38](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#38)]  
  
## Vea también  
 [Cómo: Restablecer intervalos en documentos de Word mediante programación](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Cómo: Contraer intervalos o selecciones en documentos mediante programación](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Cómo: Definir y seleccionar intervalos en documentos mediante programación](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Cómo: Recuperar los caracteres inicial y final de los intervalos mediante programación](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Cómo: Excluir marcas de párrafo al crear intervalos mediante programación](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  