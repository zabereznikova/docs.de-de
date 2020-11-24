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
ms.openlocfilehash: d8375948be5820aaf6e879b82bcfde6471cccf3f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679896"
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

 Die `SetAllThreadsDebugState` Methode wirkt sich möglicherweise auf Threads aus, die über die [EnumerateThreads-Methode](icordebugcontroller-enumeratethreads-method.md)nicht sichtbar sind, sodass Threads, die mit der-Methode angehalten wurden, mit der-Methode fortgesetzt werden `SetAllThreadsDebugState` müssen `SetAllThreadsDebugState` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
