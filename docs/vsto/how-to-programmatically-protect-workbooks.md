---
title: Procedimiento Proteger libros mediante programación
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5333504ed534373b6bb65902edb2566953de7a59
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863687"
---
# <a name="how-to-programmatically-protect-workbooks"></a>Procedimiento Proteger libros mediante programación
  Puede proteger un libro de Microsoft Office Excel para que los usuarios no se pueden agregar o eliminar hojas de cálculo y también puede desproteger el libro mediante programación. Opcionalmente, puede especificar una contraseña, indicar si desea que la estructura protegida (por lo que los usuarios no pueden mover las hojas) y que indique si desea que estén protegidas las ventanas del libro.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Proteger un libro no impide que los usuarios editen celdas. Para proteger los datos, debe proteger las hojas de cálculo. Para obtener más información, vea [Cómo: Proteger mediante programación las hojas de cálculo](../vsto/how-to-programmatically-protect-worksheets.md).  
  
 Ejemplos de código siguientes usan una variable para contener una contraseña obtenida del usuario.  
  
## <a name="protect-a-workbook-that-is-part-of-a-document-level-customization"></a>Proteger un libro que forma parte de una personalización de nivel de documento  
  
### <a name="to-protect-a-workbook"></a>Para proteger un libro  
  
1.  Llame a la <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> método del libro e incluya una contraseña. Para usar el siguiente ejemplo de código, ejecútelo la `ThisWorkbook` (clase), no en una clase de hoja.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
### <a name="to-unprotect-a-workbook"></a>Para desproteger un libro  
  
1.  Llame a la <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> método, pasando una contraseña si es necesario. Para usar el siguiente ejemplo de código, ejecútelo la `ThisWorkbook` (clase), no en una clase de hoja.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protect-a-workbook-by-using-an-application-level-add-in"></a>Proteger un libro mediante el uso de un complemento en el nivel de aplicación  
  
### <a name="to-protect-a-workbook"></a>Para proteger un libro  
  
1.  Llame a la <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> método del libro e incluya una contraseña. Este ejemplo de código usa el libro activo. Para usar este ejemplo, ejecute el código desde la clase `ThisAddIn` del proyecto.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
### <a name="to-unprotect-a-workbook"></a>Para desproteger un libro  
  
1.  Llame a la <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> método del libro activo, pasando una contraseña si es necesario. Para usar este ejemplo, ejecute el código desde la clase `ThisAddIn` del proyecto.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con libros](../vsto/working-with-workbooks.md)   
 [Cómo: Proteger mediante programación las hojas de cálculo](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Cómo: Ocultar mediante programación las hojas de cálculo](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Parámetros opcionales en las soluciones de Office](../vsto/optional-parameters-in-office-solutions.md)  
