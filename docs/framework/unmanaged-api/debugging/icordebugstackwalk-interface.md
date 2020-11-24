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
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687514"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk-Schnittstelle

Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetContext-Methode](icordebugstackwalk-getcontext-method.md)|Gibt den Kontext für den aktuellen Frame im- `ICorDebugStackWalk` Objekt zurück.|  
|[SetContext-Methode](icordebugstackwalk-setcontext-method.md)|Legt den `ICorDebugStackWalk` aktuellen Kontext des Objekts auf einen gültigen Kontext für den Thread fest.|  
|[Next-Methode](icordebugstackwalk-next-method.md)|Verschiebt das- `ICorDebugStackWalk` Objekt in den nächsten Frame.|  
|[GetFrame-Methode](icordebugstackwalk-getframe-method.md)|Ruft den aktuellen Frame im- `ICorDebugStackWalk` Objekt ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
