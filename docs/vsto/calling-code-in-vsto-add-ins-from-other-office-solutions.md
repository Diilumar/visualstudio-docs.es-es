---
title: "Llamar a c&#243;digo en complementos de VSTO desde otras soluciones de Office"
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
  - "VBA [desarrollo de Office en Visual Studio], llamar al código en complementos de nivel de aplicación"
  - "complementos de nivel de aplicación [desarrollo de Office en Visual Studio], llamar al código desde otras soluciones"
  - "llamar a código de complementos"
  - "complementos [desarrollo de Office en Visual Studio], llamar al código desde otras soluciones"
  - "interoperabilidad [desarrollo de Office en Visual Studio]"
  - "llamar a código desde VBA"
ms.assetid: c1f16b4c-9291-49ed-9694-a83a37109612
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# Llamar a c&#243;digo en complementos de VSTO desde otras soluciones de Office
  Puede exponer un objeto en su complemento VSTO para otras soluciones, incluidas otras soluciones de Microsoft Office. Esto resulta útil si su complemento VSTO proporciona un servicio que quiera habilitar para que lo usen otras soluciones. Por ejemplo, si tiene un complemento VSTO de Microsoft Office Excel que realiza cálculos sobre datos financieros desde un servicio web, otras soluciones pueden realizar estos cálculos llamando al complemento VSTO de Excel en tiempo de ejecución.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Hay dos pasos principales en este proceso:  
  
-   En el complemento VSTO, exponga un objeto a otras soluciones.  
  
-   En otra solución, acceda al objeto expuesto por el complemento VSTP y llame a los miembros del objeto.  
  
## Tipos de soluciones que pueden llamar a código en un complemento  
 Puede exponer un objeto en un complemento VSTO para los siguientes tipos de soluciones:  
  
-   Código de Visual Basic para Aplicaciones \(VBA\) en un documento que se carga en el mismo proceso de aplicación que el complemento VSTO.  
  
-   Personalizaciones de nivel de documento que se cargan en el mismo proceso de aplicación que el complemento VSTO.  
  
-   Otros complementos VSTO creados con plantillas de proyecto de Office en Visual Studio.  
  
-   Complementos COM VSTO \(es decir, complementos que implementan la interfaz <xref:Extensibility.IDTExtensibility2> directamente\).  
  
-   Cualquier solución que se ejecute en un proceso diferente que el complemento VSTO \(estos tipos de soluciones también se llaman *clientes fuera de proceso*\). Estas soluciones incluyen aplicaciones que automatizan una aplicación de Office, como Windows Forms o la aplicación de consola, y complementos VSTO que se cargan en un proceso diferente.  
  
## Exponer objetos a otras soluciones  
 Para exponer un objeto del complemento VSTO en otras soluciones, siga estos pasos en el complemento VSTO:  
  
1.  Defina una clase que quiera exponer a otras soluciones.  
  
2.  Invalide el método <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> en la clase `ThisAddIn`. Devuelva una instancia de la clase que quiere exponer a otras soluciones.  
  
### Definir la clase que quiere exponer a otras soluciones  
 Como mínimo, la clase que quiera exponer tiene que ser pública, debe tener el atributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> establecido en **true** y debe exponer la interfaz [IDispatch](http://msdn.microsoft.com/es-es/ebbff4bc-36b2-4861-9efa-ffa45e013eb5).  
  
 La manera recomendada de exponer la interfaz [IDispatch](http://msdn.microsoft.com/es-es/ebbff4bc-36b2-4861-9efa-ffa45e013eb5) es realizar los siguientes pasos:  
  
1.  Defina una interfaz que declare los miembros que quiere exponer a otras soluciones. Puede definir esta interfaz en su proyecto de complemento VSTO. Sin embargo, puede que quiera definir esta interfaz en un proyecto de biblioteca de clase diferente, si quiere exponer la clase a soluciones que no son VBA; de ese modo, las soluciones que llaman al complemento VSTO pueden hacer referencia a la interfaz sin hacer referencia al proyecto de complemento VSTO.  
  
2.  Aplique el atributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> a esta interfaz y establezca el atributo en **true**.  
  
3.  Modifique la clase para implementar esta interfaz.  
  
4.  Aplique el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> a su clase y establezca el atributo en el valor None de la enumeración <xref:System.Runtime.InteropServices.ClassInterfaceType>.  
  
5.  Si quiere exponer la clase a clientes fuera de proceso, quizás también tenga que hacer lo siguiente:  
  
    -   Derive la clase de <xref:System.Runtime.InteropServices.StandardOleMarshalObject>. Para obtener más información, vea [Exponer clases a clientes fuera de proceso](#outofproc).  
  
    -   Establezca la propiedad **Registrar para interoperabilidad COM** en el proyecto donde define la interfaz. Esto solo es necesario si quiere permitir a los clientes que usen un enlace temprano para llamar al complemento VSTO.  
  
 El siguiente ejemplo de código muestra una clase `AddInUtilities` con un método `ImportData` al que otras soluciones pueden llamar. Para ver este código en el contexto de un tutorial más amplio, consulte [Tutorial: Llamar a código en un complemento de VSTO desde VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_AddInInteropWalkthrough/CS/AddInUtilities.cs#3)]
 [!code-vb[Trin_AddInInteropWalkthrough#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_AddInInteropWalkthrough/VB/AddInUtilities.vb#3)]  
  
### Exponer clases a VBA  
 Cuando realice los pasos indicados arriba, el código VBA podrá llamar solo a los métodos que declare en la interfaz. El código VBA no puede llamar a ningún otro método de la clase, incluidos los métodos que la clase obtiene a partir de clases base, como <xref:System.Object>.  
  
 Para exponer la interfaz [IDispatch](http://msdn.microsoft.com/es-es/ebbff4bc-36b2-4861-9efa-ffa45e013eb5) también puede establecer el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> en el valor AutoDispatch o AutoDual de la enumeración <xref:System.Runtime.InteropServices.ClassInterfaceType>. Si lo hace, no tiene que declarar los métodos en una interfaz diferente. Sin embargo, el código VBA puede llamar a cualquier método público y no estático de su clase, incluidos los métodos obtenidos a partir de clases base tales como <xref:System.Object>. Además, los clientes fuera de proceso que usan enlace temprano no pueden llamar a su clase.  
  
###  <a name="outofproc"></a> Exponer clases a clientes fuera de proceso  
 Si quiere exponer una clase de su complemento de VSTO a clientes fuera de proceso, debe derivar la clase de <xref:System.Runtime.InteropServices.StandardOleMarshalObject> para asegurarse de que los clientes fuera de proceso puedan llamar al objeto de complemento de VSTO expuesto. De lo contrario, se podrían producir errores inesperados al intentar obtener una instancia del objeto expuesto en un cliente fuera de proceso.  
  
 El motivo es que todas las llamadas al modelo de objetos de una aplicación de Office deben realizarse en el subproceso principal de la interfaz de usuario, pero las llamadas al objeto desde un cliente fuera de proceso llegarán en un subproceso de RPC \(llamada a procedimiento remoto\) arbitrario. El mecanismo de cálculo de referencias COM en .NET Framework no cambiará los subprocesos y, en cambio, intentará calcular las referencias de la llamada al objeto en el subproceso de RPC entrante en lugar del subproceso principal de interfaz de usuario. Si el objeto es una instancia de una clase que deriva de <xref:System.Runtime.InteropServices.StandardOleMarshalObject>, el cálculo de las referencias de las llamadas entrantes al objeto se realizará en el subproceso donde se creó el objeto expuesto, que será el subproceso principal de interfaz de usuario de la aplicación host.  
  
 Para obtener más información sobre cómo usar subprocesos en soluciones de Office, consulte [Compatibilidad del subprocesamiento en Office](../vsto/threading-support-in-office.md).  
  
### Invalidar el método RequestComAddInAutomationService  
 El ejemplo de código siguiente muestra cómo invalidar <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> en la clase `ThisAddIn` del complemento de VSTO. En este ejemplo se da por hecho que ha definido una clase llamada `AddInUtilities` que quiere exponer a otras soluciones. Para ver este código en el contexto de un tutorial más amplio, consulte [Tutorial: Llamar a código en un complemento de VSTO desde VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_AddInInteropWalkthrough/CS/ThisAddIn.cs#1)]
 [!code-vb[Trin_AddInInteropWalkthrough#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_AddInInteropWalkthrough/VB/ThisAddIn.vb#1)]  
  
 Una vez cargado el complemento de VSTO, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] llama al método <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A>. El tiempo de ejecución asigna el objeto devuelto a la propiedad <xref:Microsoft.Office.Core.COMAddIn.Object%2A> de un objeto <xref:Microsoft.Office.Core.COMAddIn> que representa el complemento de VSTO. Este objeto <xref:Microsoft.Office.Core.COMAddIn> está disponible para otras soluciones de Office y para soluciones que automatizan Office.  
  
## Acceder a objetos desde otras soluciones  
 Para llamar al objeto expuesto en el complemento de VSTO, siga estos pasos en la solución cliente:  
  
1.  Obtenga el objeto <xref:Microsoft.Office.Core.COMAddIn> que representa el complemento de VSTO expuesto. Los clientes pueden acceder a todos los complementos de VSTO disponibles usando la propiedad Application.COMAddIns del modelo de objetos de la aplicación host de Office.  
  
2.  Acceda a la propiedad <xref:Microsoft.Office.Core.COMAddIn.Object%2A> del objeto <xref:Microsoft.Office.Core.COMAddIn>. Esta propiedad devuelve el objeto expuesto desde el complemento de VSTO.  
  
3.  Llame a los miembros del objeto expuesto.  
  
 La manera en que usa el valor devuelto de la propiedad <xref:Microsoft.Office.Core.COMAddIn.Object%2A> en los clientes VBA es diferente de los clientes que no son VBA. En los clientes fuera de proceso, es necesario código adicional para evitar una posible condición de carrera.  
  
### Acceder a objetos desde soluciones VBA  
 El ejemplo de código siguiente muestra cómo usar VBA para llamar a un método expuesto por un complemento de VSTO. Esta macro de VBA llama a un método llamado `ImportData` que está definido en un complemento de VSTO llamado **ExcelImportData**. Para ver este código en el contexto de un tutorial más amplio, consulte [Tutorial: Llamar a código en un complemento de VSTO desde VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
```  
Sub CallVSTOMethod() Dim addIn As COMAddIn Dim automationObject As Object Set addIn = Application.COMAddIns("ExcelImportData") Set automationObject = addIn.Object automationObject.ImportData End Sub  
```  
  
### Acceder a objetos desde soluciones que no son VBA  
 En una solución que no es VBA, debe convertir el valor de propiedad <xref:Microsoft.Office.Core.COMAddIn.Object%2A> en la interfaz que implementa y, después, puede llamar a los métodos expuestos en el objeto de interfaz. El ejemplo de código siguiente muestra cómo llamar al método `ImportData` desde un complemento de VSTO diferente que se creó usando las herramientas de desarrollador de Office en Visual Studio.  
  
```vb  
Dim addIn As Office.COMAddIn = Globals.ThisAddIn.Application.COMAddIns.Item("ExcelImportData") Dim utilities As ExcelImportData.IAddInUtilities = TryCast( _ addIn.Object, ExcelImportData.IAddInUtilities) utilities.ImportData()  
```  
  
```csharp  
object addInName = "ExcelImportData"; Office.COMAddIn addIn = Globals.ThisAddIn.Application.COMAddIns.Item(ref addInName); ExcelImportData.IAddInUtilities utilities = (ExcelImportData.IAddInUtilities)addIn.Object; utilities.ImportData();  
```  
  
 En este ejemplo, si intenta convertir el valor de la propiedad <xref:Microsoft.Office.Core.COMAddIn.Object%2A> en la clase `AddInUtilities` en lugar de la interfaz `IAddInUtilities`, el código iniciará una <xref:System.InvalidCastException>.  
  
## Vea también  
 [Programar complementos de VSTO](../vsto/programming-vsto-add-ins.md)   
 [Tutorial: Llamar a código en un complemento de VSTO desde VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)   
 [Desarrollar soluciones de Office](../vsto/developing-office-solutions.md)   
 [Cómo: Crear proyectos de Office en Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Arquitectura de complementos de VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Personalizar características de la interfaz de usuario mediante interfaces de extensibilidad](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)  
  
  