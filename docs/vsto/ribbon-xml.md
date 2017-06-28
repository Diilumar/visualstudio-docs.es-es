---
title: "XML de la cinta de opciones"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VSTO.Ribbon.RibbonXMLItem"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "cinta personalizada, XML"
  - "personalizar la cinta, XML"
  - "Cinta [desarrollo de Office en Visual Studio], XML"
  - "métodos de devolución de llamada"
  - "personalizar la cinta, mostrar"
  - "personalizar la cinta, definir el comportamiento"
  - "XML [desarrollo de Office en Visual Studio], cinta"
  - "personalizar la cinta, definir el comportamiento"
  - "Cinta [desarrollo de Office en Visual Studio], personalizar"
  - "personalizar la cinta, mostrar"
ms.assetid: a5945667-40e8-4191-9f1e-71c18ec30a2e
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# XML de la cinta de opciones
  El elemento Cinta \(XML\) le permite personalizar una cinta de opciones mediante XML. Use el elemento Cinta \(XML\) si desea personalizar la cinta de opciones de un modo que el elemento Ribbon \(diseñador visual\) no admite. Para obtener una comparación de lo que puede hacer con cada elemento, vea [Información general sobre la cinta de opciones](../vsto/ribbon-overview.md).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## Agregar un elemento Cinta \(XML\) a un proyecto  
 Puede agregar un elemento **Cinta \(XML\)** a cualquier proyecto de Office desde el cuadro de diálogo **Agregar nuevo elemento**. Visual Studio agrega automáticamente los siguientes archivos al proyecto:  
  
-   Un archivo XML de la cinta de opciones. Este archivo define la interfaz de usuario de la cinta de opciones. Use este archivo para agregar elementos de la interfaz de usuario, como pestañas, grupos y controles. Para obtener información detallada, consulte [Referencia de archivo XML de la cinta de opciones](#RibbonDescriptorFile) más adelante en este tema.  
  
-   Un archivo de código de la cinta de opciones. Este archivo contiene la *clase Ribbon*. Esta clase tiene el nombre que especificó para el elemento **Cinta \(XML\)**  en el cuadro de diálogo **Agregar nuevo elemento**. Las aplicaciones de Microsoft Office usan una instancia de esta clase para cargar la cinta de opciones personalizada. Para obtener información detallada, consulte [Referencia de la clase Ribbon](#RibbonExtensionClass) más adelante en este tema.  
  
 De forma predeterminada, estos archivos agregan un grupo personalizado a la pestaña **Complementos** en la cinta de opciones.  
  
## Mostrar la cinta de opciones personalizada en una aplicación de Microsoft Office  
 Después de agregar un elemento **Cinta \(XML\)** al proyecto, debe agregar código a la clase **ThisAddin**, **ThisWorkbook** o **ThisDocument**, que reemplaza el método CreateRibbonExtensibilityObject y devuelve la clase XML Ribbon a la aplicación de Office.  
  
 En el siguiente código de ejemplo se reemplaza el método CreateRibbonExtensibilityObject y devuelve una clase XML Ribbon llamada MyRibbon.  
  
 [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/CS/ThisAddIn.cs#1)]
 [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/VB/ThisAddIn.vb#1)]  
  
## Definir el comportamiento de la cinta de opciones personalizada  
 Puede responder a las acciones del usuario, como hacer clic en un botón de la cinta de opciones, creando  *métodos de devolución de llamada*. Los métodos de devolución de llamada son similares a los eventos de los controles de Windows Forms, pero se identifican con un atributo en el código XML del elemento de la interfaz de usuario. Cuando escribe métodos en la clase Ribbon, un control llama al método que tiene el mismo nombre que el valor del atributo. Por ejemplo, puede crear un método de devolución de llamada al que se llama cuando un usuario hace clic en un botón de la cinta de opciones. Es necesario llevar a cabo dos pasos para crear un método de devolución de llamada:  
  
-   Asigne a un control del archivo XML de la cinta de opciones un atributo que identifique un método de devolución de llamada en el código.  
  
-   Defina el método de devolución de llamada en la clase Ribbon.  
  
> [!NOTE]  
>  Outlook requiere un paso adicional. Para obtener más información, consulta [Personalizar una cinta de opciones para Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
 Para ver un tutorial en el que se muestra cómo se automatiza una aplicación desde la cinta de opciones, consulte [Tutorial: Crear una pestaña personalizada usando XML de la cinta de opciones](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md).  
  
### Asignar métodos de devolución de llamada a controles  
 Para asignar un método de devolución de llamada a un control en el archivo XML de la cinta de opciones, agregue un atributo que especifique el tipo del método de devolución de llamada y el nombre del método. Por ejemplo, el siguiente elemento define un botón de alternancia que tiene un método de devolución de llamada **onAction** llamado `OnToggleButton1`.  
  
```  
<toggleButton id="toggleButton1" onAction="OnToggleButton1" />  
```  
  
 Se llama a **onAction** cuando el usuario efectúa la tarea principal asociada a un control determinado. Por ejemplo, se llama al método de devolución de llamada **onAction** de un botón de alternancia cuando el usuario hace clic en el botón.  
  
 El método que especifique en el atributo puede tener cualquier nombre. Sin embargo, debe coincidir con el nombre del método que defina en el archivo de código de la cinta de opciones.  
  
 Hay muchos tipos diferentes de métodos de devolución de llamada que se pueden asignar a los controles de la cinta de opciones. Para obtener una lista completa de los métodos de devolución de llamada disponibles para cada control, consulte el artículo técnico [Personalizar la interfaz de usuario de la cinta de opciones de Office \(2007\) para desarrolladores \(parte 3 de 3\)](http://msdn.microsoft.com/es-es/a16c7df5-93f3-4920-baa8-7b7290794c15).  
  
###  <a name="CallBackMethods"></a> Definir métodos de devolución de llamada  
 Defina los métodos de devolución de llamada en la clase Ribbon en el archivo de código de la cinta de opciones. Un método de devolución de llamada tiene varios requisitos:  
  
-   Debe declararse como público.  
  
-   Su nombre debe coincidir con el nombre de un método de devolución de llamada asignado a un control en el archivo XML de la cinta de opciones.  
  
-   Su firma debe coincidir con la de un tipo de método de devolución de llamada que esté disponible para el control de cinta de opciones asociado.  
  
 Para obtener una lista completa de las firmas de métodos de devolución de llamada para los controles de la cinta de opciones, consulte el artículo técnico [Personalizar la interfaz de usuario de la cinta de opciones de Office \(2007\) para desarrolladores \(parte 3 de 3\)](http://msdn.microsoft.com/es-es/a16c7df5-93f3-4920-baa8-7b7290794c15). Visual Studio no proporciona compatibilidad con IntelliSense para los métodos de devolución de llamada que se crean en el archivo de código de la cinta de opciones. Si crea un método de devolución de llamada que no coincide con una firma válida, se compilará el código, pero no ocurrirá nada cuando el usuario haga clic en el control.  
  
 Todos los métodos de devolución de llamada tienen un parámetro <xref:Microsoft.Office.Core.IRibbonControl> que representa el control que llamó al método. Puede usar este parámetro para reutilizar el mismo método de devolución de llamada en varios controles. En el siguiente ejemplo de código se muestra un método de devolución de llamada **onAction** que efectúa diferentes tareas según el control en el que el usuario hace clic.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_RibbonOutlookBasic/CS/Ribbon1.cs#2)]
 [!code-vb[Trin_RibbonOutlookBasic#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_RibbonOutlookBasic/VB/Ribbon1.vb#2)]  
  
##  <a name="RibbonDescriptorFile"></a> Referencia de archivo XML de la cinta de opciones  
 Puede definir su cinta de opciones personalizada agregando elementos y atributos al archivo XML de la cinta de opciones. De forma predeterminada, el archivo XML de la cinta de opciones contiene el siguiente código XML.  
  
```  
<?xml version="1.0" encoding="UTF-8"?> <customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui" onLoad="OnLoad"> <ribbon> <tabs> <tab idMso="TabAddIns"> <group id="MyGroup" label="My Group"> </group> </tab> </tabs> </ribbon> </customUI>  
```  
  
 En la siguiente tabla se describen los elementos predeterminados del archivo XML de la cinta de opciones.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|**customUI**|Representa la cinta de opciones personalizada en el proyecto de complemento de VSTO.|  
|**ribbon**|Representa la cinta de opciones.|  
|**tabs**|Representa un conjunto de pestañas de la cinta de opciones.|  
|**tab**|Representa una sola pestaña de la cinta de opciones.|  
|**group**|Representa un grupo de controles en la pestaña de la cinta de opciones.|  
  
 Estos elementos tienen atributos que especifican la apariencia y el comportamiento de la cinta de opciones personalizada. En la siguiente tabla se describen los atributos predeterminados del archivo XML de la cinta de opciones.  
  
|Atributo|Elemento primario|Descripción|  
|--------------|-----------------------|-----------------|  
|**onLoad**|**customUI**|Identifica un método al que se llama cuando la aplicación carga la cinta de opciones.|  
|**idMso**|**tab**|Identifica una pestaña integrada que se muestra en la cinta de opciones.|  
|**id**|**group**|Identifica el grupo.|  
|**label**|**group**|Especifica el texto que aparece en el grupo.|  
  
 Los elementos y atributos predeterminados del archivo XML de la cinta de opciones son un subconjunto pequeño de los elementos y atributos disponibles. Para obtener una lista completa de los elementos y atributos disponibles, consulte el artículo técnico [Personalizar la interfaz de usuario de la cinta de opciones de Office \(2007\) para desarrolladores \(parte 2 de 3\)](http://msdn.microsoft.com/es-es/6b904f55-525f-4520-9b81-a017db65657b).  
  
##  <a name="RibbonExtensionClass"></a> Referencia de la clase Ribbon  
 Visual Studio genera la clase Ribbon en el archivo de código de la cinta de opciones. Agregue a esta clase los métodos de devolución de llamada para los controles de la cinta de opciones. Esta clase implementa la interfaz <xref:Microsoft.Office.Core.IRibbonExtensibility>.  
  
 En la siguiente tabla se describen los métodos predeterminados de esta clase.  
  
|Método|Descripción|  
|------------|-----------------|  
|`GetCustomUI`|Devuelve el contenido del archivo XML de la cinta de opciones. Las aplicaciones de Microsoft Office llaman a este método para obtener una cadena XML que define la interfaz de usuario de la cinta personalizada. Este método implementa el método <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A>. **Note:**  `GetCustomUI` solo debe implementarse para devolver el contenido del archivo XML de la cinta de opciones; no se debe usar para inicializar el complemento de VSTO. En particular, no debe intentar mostrar cuadros de diálogo u otras ventanas en la implementación `GetCustomUI`. De lo contrario, puede que el comportamiento de la cinta de opciones personalizada no sea correcto. Si tiene que ejecutar código que inicialice el complemento de VSTO, agréguelo al controlador de eventos `ThisAddIn_Startup`.|  
|`OnLoad`|Asigne el parámetro <xref:Microsoft.Office.Core.IRibbonControl> al campo `ribbon`. Las aplicaciones de Microsoft Office llaman a este método cuando cargan la cinta de opciones personalizada. Puede usar este campo para actualizar dinámicamente la cinta personalizada. Para obtener más información, consulte el artículo técnico [Personalizar la interfaz de usuario de la cinta de opciones de Office \(2007\) para desarrolladores \(parte 1 de 3\)](http://msdn.microsoft.com/es-es/a4fd6d18-d4a8-4e64-bd89-f437208573d3).|  
|`GetResourceText`|Lo llama el método `GetCustomUI` para obtener el contenido del archivo XML de la cinta de opciones.|  
  
## Vea también  
 [Información general sobre la cinta de opciones](../vsto/ribbon-overview.md)   
 [Tutorial: Crear una pestaña personalizada usando XML de la cinta de opciones](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [Personalización de la interfaz de usuario de Office](../vsto/office-ui-customization.md)  
  
  