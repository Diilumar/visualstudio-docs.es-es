---
title: Nodos de parámetros | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bed941a35af21b78ea5159a218ccd36d2ff5f1e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47583141"
---
# <a name="parameter-nodes"></a>Nodos de parámetros
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [nodos de parámetros](https://docs.microsoft.com/visualstudio/designers/parameter-nodes).  
  
En el Diseñador de sombras, los nodos de parámetro representan entradas al sombreador que están bajo el control de la aplicación por cada dibujo, por ejemplo, propiedades de material, luces direccionales, posición de la cámara y tiempo. Dado que se pueden cambiar estos parámetros con cada llamada a draw, se puede usar el mismo sombreador para proporcionar diferentes aspectos a un objeto.  
  
## <a name="parameter-node-reference"></a>Referencia de nodos de parámetro  
  
|Nodo|Detalles|Propiedades|  
|----------|-------------|----------------|  
|**Posición global de la cámara**|Posición de la cámara en el espacio global.<br /><br /> **Salida:**<br /><br /> `Output`: `float4`<br /> Posición de la cámara.|Ninguna|  
|**Dirección de la luz**|El vector que define la dirección en la que se proyecta la luz desde una fuente de luz en el espacio global.<br /><br /> Se puede usar para calcular las contribuciones de reflexión especular y de iluminación en el espacio global.<br /><br /> **Salida:**<br /><br /> `Output`: `float3`<br /> El vector desde el píxel actual a una fuente de luz.|Ninguna|  
|**Color ambiental de material**|La contribución de color difuso del píxel actual que se atribuye a la iluminación indirecta.<br /><br /> El color difuso de un píxel simula cómo interactúa la iluminación con superficies desiguales. Se puede usar el parámetro Color ambiental de material para determinar aproximadamente cómo contribuye la iluminación indirecta a la apariencia de un objeto en el mundo real.<br /><br /> **Salida:**<br /><br /> `Output`: `float4`<br /> El color difuso del píxel actual debido a la iluminación indirecta o ambiental.|**Acceso**<br /> **Público** para que esta propiedad se pueda establecer desde el Editor de modelos. De lo contrario, **Privado**.<br /><br /> **Valor**<br /> El color difuso del píxel actual debido a la iluminación indirecta o ambiental.|  
|**Color difuso de material**|Un color que describe cómo difumina la iluminación directa el píxel actual.<br /><br /> El color difuso de un píxel simula cómo interactúa la iluminación con superficies desiguales. Se puede usar el parámetro Color difuso de material para cambiar cómo difumina el píxel actual la iluminación directa, es decir, la luz direccional, puntual y focal.<br /><br /> **Salida:**<br /><br /> `Output`: `float4`<br /> Un color que describe cómo difumina la iluminación directa el píxel actual.|**Acceso**<br /> **Público** para que esta propiedad se pueda establecer desde el Editor de modelos. De lo contrario, **Privado**.<br /><br /> **Valor**<br /> Un color que describe cómo difumina la iluminación directa el píxel actual.|  
|**Color emisor de luz de material**|La contribución de color del píxel actual que se atribuye a la iluminación que se le proporciona.<br /><br /> Se puede usar para simular un objeto resplandeciente, es decir, aquel que proporciona su propia luz. Esta luz no afecta a otros objetos.<br /><br /> **Salida:**<br /><br /> `Output`: `float4`<br /> La contribución de color del píxel actual debida a la iluminación propia proporcionada.|**Acceso**<br /> **Público** para que esta propiedad se pueda establecer desde el Editor de modelos. De lo contrario, **Privado**.<br /><br /> **Valor**<br /> La contribución de color del píxel actual debida a la iluminación propia proporcionada.|  
|**Reflexión especular de material**|Un color que describe cómo refleja la iluminación directa el píxel actual.<br /><br /> El color especular de un píxel simula cómo interactúa la iluminación con superficies suaves y reflectantes. Se puede usar el parámetro Reflexión especular de material para cambiar cómo refleja el píxel actual la iluminación directa, es decir, la luz direccional, puntual y focal.<br /><br /> **Salida:**<br /><br /> `Output`: `float4`<br /> Un color que describe cómo refleja la iluminación directa el píxel actual.|**Acceso**<br /> **Público** para que esta propiedad se pueda establecer desde el Editor de modelos. De lo contrario, **Privado**.<br /><br /> **Valor**<br /> Un color que describe cómo refleja la iluminación directa el píxel actual.|  
|**Potencia especular de material**|Valor escalar que describe la intensidad de los reflejos especulares.<br /><br /> Cuanto mayor sea la potencia especular, más intensidad y alcance tiene la iluminación especular.<br /><br /> **Salida:**<br /><br /> `Output`: `float`<br /> Un término exponencial que describe la intensidad de los reflejos especulares en el píxel actual.|**Acceso**<br /> **Público** para que esta propiedad se pueda establecer desde el Editor de modelos. De lo contrario, **Privado**.<br /><br /> **Valor**<br /> El exponente que define la intensidad de los reflejos especulares en el píxel actual.|  
|**Tiempo normalizado**|El tiempo en segundos, normalizado en el intervalo [0, 1], de forma que cuando el tiempo llega a 1, se restablece en 0.<br /><br /> Se puede usar como parámetro en los cálculos del sombreador, por ejemplo, para animar coordenadas de textura, valores de color u otros atributos.<br /><br /> **Salida:**<br /><br /> `Output`: `float`<br /> El tiempo normalizado, en segundos.|Ninguna|  
|**Tiempo**|Tiempo en segundos.<br /><br /> Se puede usar como parámetro en los cálculos del sombreador, por ejemplo, para animar coordenadas de textura, valores de color u otros atributos.<br /><br /> **Salida:**<br /><br /> `Output`: `float`<br /> El tiempo, en segundos.|Ninguna|


