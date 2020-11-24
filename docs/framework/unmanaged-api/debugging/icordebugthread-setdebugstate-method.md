---
title: ICorDebugThread::SetDebugState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: e28d37e4477862ff2ebeeb05ea5f5386e157cd83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678727"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState-Methode

Legt Flags fest, die den Debugzustand dieses ICorDebugThread beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `state`  
 in Eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den Debugzustand dieses Threads angeben.  
  
## <a name="remarks"></a>Hinweise  

 `SetDebugState` Legt den aktuellen Debugzustand des Threads fest. (Der "aktuelle Debugzustand" stellt den Debugzustand dar, wenn der Prozess fortgesetzt werden soll, und nicht der tatsächliche aktuelle Zustand.) Der normale Wert hierfür ist THREAD_RUN. Nur der Debugger kann sich auf den Debugzustand eines Threads auswirken. Die debugzustände werden am Ende fortgesetzt. Wenn Sie also einen Thread THREAD_SUSPENDed über mehrere Vorgänge hinweg beibehalten möchten, können Sie ihn einmal festlegen und sich danach nicht mehr darum kümmern. Das Anhalten von Threads und das Fortsetzen des Prozesses kann zu Deadlocks führen, obwohl dies in der Regel unwahrscheinlich ist. Dies ist eine systeminterne Qualität von Threads und Prozessen und ist Entwurfs bedingt. Ein Debugger kann die Threads asynchron unterbrechen und fortsetzen, um den Deadlock zu unterbrechen. Wenn der Benutzer Zustand des Threads USER_UNSAFE_POINT enthält, kann der Thread eine Garbage Collection (GC) blockieren. Dies bedeutet, dass der angehaltene Thread eine viel höhere Wahrscheinlichkeit hat, dass ein Deadlock verursacht wird. Dies wirkt sich möglicherweise nicht auf Debugereignisse aus Daher sollte ein Debugger die gesamte Ereignis Warteschlange (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) abgleichen, bevor Threads angehalten oder fortgesetzt werden. Andernfalls werden möglicherweise Ereignisse in einem Thread angezeigt, der davon ausgeht, dass er bereits angehalten wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
