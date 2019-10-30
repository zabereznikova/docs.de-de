---
title: ICorDebugController::SetAllThreadsDebugState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: 1190f83e2671216cf1627eeb710ba576e4b2ec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125362"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState-Methode
Legt den Debugstatus aller verwalteten Threads im Prozess fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `state`  
 in Ein Wert der CorDebugThreadState-Enumeration, der den Zustand des Threads für das Debuggen angibt.  
  
 `pExceptThisThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das einen Thread darstellt, der von der Debug-Statuseinstellung ausgenommen werden soll. Wenn dieser Wert NULL ist, wird kein Thread ausgenommen.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetAllThreadsDebugState`-Methode wirkt sich möglicherweise auf Threads aus, die über die [EnumerateThreads-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)nicht sichtbar sind, sodass Threads, die mit der `SetAllThreadsDebugState`-Methode angehalten wurden, mit der `SetAllThreadsDebugState`-Methode fortgesetzt werden müssen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
