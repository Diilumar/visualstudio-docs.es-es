---
title: IDebugApplicationNode100 (interfaz) | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100 Interface
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a6cbe92c6789b702adc69f598a995f84c01ef86
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347460"
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 (Interfaz)
El `IDebugApplicationNode100` interfaz extiende la funcionalidad de la [IDebugApplicationNode (interfaz)](../../winscript/reference/idebugapplicationnode-interface.md). Puede obtener una instancia de esta interfaz llamando a QueryInterface en una implementación de [IDebugApplicationNode (interfaz)](../../winscript/reference/idebugapplicationnode-interface.md).  
  
> [!IMPORTANT]
>  Esta interfaz se implementa mediante PDM v10.0 y versiones posteriores. Se encuentra en activdbg100.h.  
  
## <a name="methods"></a>Métodos  
 La interfaz `IDebugApplicationNode100` expone los métodos siguientes.  
  
|Método|Descripción|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|Obtiene los documentos de texto que están ocultos por el filtro especificado.|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|Determina si el documento especificado pertenece a uno de los nodos secundarios de este nodo.|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|Establece el filtro en un determinado [IDebugApplicationNodeEvents (interfaz)](../../winscript/reference/idebugapplicationnodeevents-interface.md) implementación. Permite a los depuradores de scripts filtrar los nodos de aplicación secundarios generados por el compilador para que el PDM no volverá a enviar eventos cuando se crea o se quitan los nodos. De forma predeterminada, se enviarán todos los nodos.|