---
title: 'Vista Llamador y destinatario: datos de muestreo de memoria de .NET | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Caller/Callee view
ms.assetid: 36f5b4de-5686-4f40-9e72-f4aee27d833c
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04ba2a522c6accb9dcb5e316ea8c63beb260e739
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47575669"
---
# <a name="callercallee-view---net-memory-sampling-data"></a>Vista Llamador y destinatario: datos de muestreo de memoria de .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [vista llamador y destinatario: datos de muestreo de memoria de .NET](https://docs.microsoft.com/visualstudio/profiling/caller-callee-view-dotnet-memory-sampling-data).  
  
La vista Llamador y destinatario muestra datos de la generación de perfiles de memoria de. NET para una función seleccionada y sus funciones primarias y secundarias. La vista Llamador y destinatario contiene tres cuadrículas.  
  
 **Función actual** se muestra en la cuadrícula central e incluye información sobre la generación de perfiles de memoria de la función seleccionada. Los valores incluyen todas las llamadas a la función que se muestrearon.  
  
 **Funciones que llamaron a la función actual** se muestra en la cuadrícula superior e incluye la cantidad del valor de la función seleccionada (actual) generado por llamadas desde la función de llamador (primaria).  
  
 **Funciones llamadas por la función actual** se muestra en la cuadrícula inferior e incluye datos de generación de perfiles de memoria para las funciones de destinatario (secundarias) de la función seleccionada cuando la función actual llamó a la función secundaria.  
  
 Haga doble clic en una fila de función de llamador o destinatario para hacer que esa fila sea la función actual.  
  
|Columna|Descripción|  
|------------|-----------------|  
|**Identificador del proceso**|Identificador de proceso (PID) de la ejecución de generación de perfiles.|  
|**Nombre de proceso**|Nombre del proceso.|  
|**Nombre del módulo**|Nombre del módulo que contiene la función.|  
|**Ruta de acceso del módulo**|Ruta de acceso del módulo que contiene la función.|  
|**Archivo de código fuente**|Archivo de origen que contiene la definición de esta función.|  
|**Nombre de la función**|El nombre completo de la función.|  
|**Número de línea de la función**|Número de línea del inicio de esta función en el archivo de origen.|  
|**Dirección de la función**|Dirección de la función.|  
|**Type**|El contexto de la función:<br /><br /> **0**: la función actual<br /><br /> **1**: una función que llama a la función actual<br /><br /> **2**: una función llamada por la función actual<br /><br /> Solo disponible en los informes de línea de comandos de [VSPerfReport](../profiling/vsperfreport.md).|  
|**Nivel**|La profundidad de esta función en el árbol de llamadas. Solo disponible en los informes de línea de comandos de [VSPerfReport](../profiling/vsperfreport.md).|  
|**Asignaciones inclusivas**|-   En la función actual, el número de objetos asignados por la función en la ejecución de la generación de perfiles. Este número incluye los objetos creados en funciones de destinatario.<br />-   En una función de llamador, el número de asignaciones inclusivas de la función actual generadas por llamadas de esta función.<br />-   En una función de destinatario, el número de objetos asignados por las instancias de esta función a las que llamó la función actual. El número incluye las asignaciones realizadas por funciones a las que llamó la función de destinatario.|  
|**Porcentaje de asignaciones inclusivas**|El porcentaje de todos los objetos que se crearon durante la ejecución de la generación de perfiles que eran asignaciones inclusivas de esta función.|  
|**Asignaciones exclusivas**|-   En la función actual, el número de objetos creados cuando la función estaba ejecutando código del cuerpo de la función (es decir, cuando la función estaba en la parte superior de la pila de llamadas). El número no incluye los objetos creados en funciones a las que llamó la función.<br />-   En una función de llamador, el número de asignaciones exclusivas de la función actual generadas por llamadas de esta función.<br />-   En una función de destinatario, el número de objetos creados por las instancias de esta función a las que llamó la función actual. El número no incluye los objetos creados por funciones a las que llamó la función de destinatario.|  
|**Porcentaje de asignaciones exclusivas**|El porcentaje de todos los objetos que se crearon durante la ejecución de la generación de perfiles que eran asignaciones inclusivas de esta función.|  
|**Bytes inclusivos**|-   En la función actual, el número de bytes de memoria asignados por la función en la ejecución de la generación de perfiles. El número incluye la memoria asignada en las funciones a las que llamó esta función.<br />-   En una función de llamador, el número de bytes inclusivos de la función actual generados por llamadas de la función de llamador.<br />-   En una función de destinatario, el número de bytes asignados por las instancias de esta función generadas por llamadas de la función actual. El número incluye los bytes asignados por las funciones a las que llamó la función de destinatario.|  
|**Porcentaje de bytes inclusivos**|El porcentaje de todos los bytes de memoria que se asignaron durante la ejecución de la generación de perfiles que eran asignaciones inclusivas de esta función.|  
|**Bytes exclusivos**|-   En la función actual, el número de bytes de memoria asignados por la función en la ejecución de la generación de perfiles. Este número no incluye la memoria asignada por las funciones a las que llamó la función actual.<br />-   En una función de llamador, el número de bytes exclusivos de la función actual generados por llamadas de la función de llamador.<br />-   En una función de destinatario, el número de bytes asignados por las instancias de la función generadas por llamadas de la función actual. El número no incluye los bytes asignados por las funciones a las que llamó la función de destinatario.|  
|**Porcentaje de bytes exclusivos**|El porcentaje de todos los bytes de memoria que se asignaron durante la ejecución de la generación de perfiles que eran asignaciones exclusivas de esta función.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Personalizar las columnas de la vista de informes](../profiling/how-to-customize-report-view-columns.md)   
 [Vista Llamador y destinatario: datos de instrumentación de memoria .NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Vista Llamador y destinatario: datos de muestreo](../profiling/caller-callee-view-sampling-data.md)   
 [Vista Llamador y destinatario: datos de instrumentación](../profiling/caller-callee-view-instrumentation-data.md)


