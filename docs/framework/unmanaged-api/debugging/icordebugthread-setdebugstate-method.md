---
title: ICorDebugThread::SetDebugState-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.SetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState-Methode
Legt die Flags, die den Debugzustand ICorDebugThread beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `state`  
 [in] Eine bitweise Kombination von Werten der CorDebugThreadState-Enumeration, die den Debugzustand dieses Threads angeben.  
  
## <a name="remarks"></a>Hinweise  
 `SetDebugState`Legt den aktuellen Debugzustand des Threads fest. ("Aktuellen Debugzustand" stellt den Debugzustand, wäre der Vorgang fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status.) Der normale Wert ist THREAD_RUNNING. Nur der Debugger kann den Debugzustand eines Threads beeinträchtigen. Debuggen Sie die Zustände zuletzt über fortgesetzt wird, sodass, wenn Sie einen Thread THREAD_SUSPENDed über mehrere weiterhin beibehalten möchten, können Sie es einmal festgelegt und danach nicht kümmern müssen. Unterbrechen von Threads und den Vorgang fortsetzen können Deadlocks verursachen, obwohl es eher unwahrscheinlich ist. Dies ist eine systeminterne Qualität von Threads und Prozessen und entwurfsbedingten. Ein Debugger kann asynchron unterbrechen und Fortsetzen der Threads, um den Deadlock zu durchbrechen. Wenn der Thread des Benutzerzustands USER_UNSAFE_POINT enthält, kann der Thread eine Garbagecollection (GC) blockiert. Dies bedeutet, dass der unterbrochene Thread eine viel höhere Chance, dass einen Deadlock verursacht hat. Dies kann keinen Einfluss auf Debuggen Ereignisse bereits in der Warteschlange. Daher sollte ein Debugger die gesamte Ereigniswarteschlange ausgleichen (durch Aufrufen von [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) vor dem Anhalten oder Fortsetzen von Threads. Andernfalls treten möglicherweise auf sie Ereignisse in einem Thread, die sie der Meinung ist, dass er bereits angehalten wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
