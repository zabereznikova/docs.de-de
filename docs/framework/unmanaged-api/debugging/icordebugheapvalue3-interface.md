---
title: ICorDebugHeapValue3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: ddfe8cee8fdbca910ffa4f6989b1359ae5f7b11f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794379"
---
# <a name="icordebugheapvalue3-interface"></a>ICorDebugHeapValue3-Schnittstelle
Macht die Bildschirmsperreigenschaften von Objekten verfügbar. Diese Schnittstelle erweitert die ICorDebugHeapValue-und ICorDebugHeapValue2-Schnittstellen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetThreadOwningMonitorLock-Methode](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|Gibt den verwalteten Thread zurück, der die Monitor Sperre für dieses Objekt besitzt.|  
|[GetMonitorEventWaitList-Methode](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|Stellt eine geordnete Liste von Threads bereit, die für das-Ereignis in die Warteschlange eingereiht werden, das einer Monitor Sperre zugeordnet ist.|  
  
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
