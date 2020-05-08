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
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976589"
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
 Die `SetAllThreadsDebugState` Methode wirkt sich möglicherweise auf Threads aus, die über die [EnumerateThreads-Methode](icordebugcontroller-enumeratethreads-method.md)nicht sichtbar sind, `SetAllThreadsDebugState` sodass Threads, die mit der-Methode `SetAllThreadsDebugState` angehalten wurden, mit der-Methode fortgesetzt werden müssen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
