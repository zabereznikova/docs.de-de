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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499692"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState-Methode
Flags, die beschreiben, den Debugzustand ICorDebugThread festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `state`  
 [in] Eine bitweise Kombination von Werten der CorDebugThreadState-Enumeration, die den Debugzustand dieses Threads angeben.  
  
## <a name="remarks"></a>Hinweise  
 `SetDebugState` Legt den aktuellen Debugzustand des Threads fest. (Der "aktuellen Debugzustand" stellt den Debugzustand dar, würde der Vorgang fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status.) Der normale Wert für diesen ist THREAD_RUNNING. Nur der Debugger kann den Debugzustand eines Threads beeinträchtigen. Debuggen Sie Zustände zuletzt über fortgesetzt wird, sodass Wenn einen Thread THREAD_SUSPENDed über mehrere weiterhin beibehalten werden sollen, können Sie es einmal festgelegt und danach keine Gedanken. Anhalten von Threads und den Vorgang fortsetzen können Deadlocks verursachen, obwohl dies eher unwahrscheinlich ist. Dies ist eine systeminterne Qualität von Threads und Prozessen und standardmäßig. Ein Debugger kann asynchron unterbrechen und Fortsetzen von Threads um den Deadlock zu durchbrechen. Wenn der Thread des Benutzerstatus USER_UNSAFE_POINT enthält, kann der Thread eine Garbagecollection (GC) blockiert. Dies bedeutet, dass der unterbrochene Thread eine viel höhere Chance und einen Deadlock verursachen. Dies beeinflusst möglicherweise nicht debuggen, die Ereignisse bereits in der Warteschlange. Daher sollte ein Debugger die gesamte Ereigniswarteschlange abzuleiten (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) vor dem Anhalten oder Fortsetzen von Threads. Andernfalls kann es Ereignisse in einem Thread ab, die er glaubt, dass sie bereits angehalten wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
