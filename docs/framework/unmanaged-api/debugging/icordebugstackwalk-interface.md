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
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791878"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk-Schnittstelle
Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetContext-Methode](icordebugstackwalk-getcontext-method.md)|Gibt den Kontext für den aktuellen Frame im `ICorDebugStackWalk` Objekt zurück.|  
|[SetContext-Methode](icordebugstackwalk-setcontext-method.md)|Legt den aktuellen Kontext des `ICorDebugStackWalk` Objekts auf einen gültigen Kontext für den Thread fest.|  
|[Next-Methode](icordebugstackwalk-next-method.md)|Verschiebt das `ICorDebugStackWalk` Objekt in den nächsten Frame.|  
|[GetFrame-Methode](icordebugstackwalk-getframe-method.md)|Ruft den aktuellen Frame im `ICorDebugStackWalk` Objekts ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
