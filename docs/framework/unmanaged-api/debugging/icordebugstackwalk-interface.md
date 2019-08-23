---
title: ICorDebugStackWalk-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959672"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk-Schnittstelle
Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Gibt den Kontext für den aktuellen Frame im `ICorDebugStackWalk` -Objekt zurück.|  
|[SetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Legt den `ICorDebugStackWalk` aktuellen Kontext des Objekts auf einen gültigen Kontext für den Thread fest.|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Verschiebt das `ICorDebugStackWalk` -Objekt in den nächsten Frame.|  
|[GetFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Ruft den aktuellen Frame im `ICorDebugStackWalk` -Objekt ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
