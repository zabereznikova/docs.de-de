---
title: ICorProfilerCallback::RuntimeSuspendStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: b778088f53a3c49def95d715f5fefcb26af81489
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731981"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted-Methode

Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads aussetzen soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>Parameter  

 `suspendReason`  
 in Ein Wert der [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) -Enumeration, die den Grund für die Unterbrechung angibt.  
  
## <a name="remarks"></a>Hinweise  

 Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben. An diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die zur Laufzeit gelangen. Alle Threads in der Laufzeit werden entweder sofort angehalten, wenn Sie sich bereits in interruptebarem Code befinden, oder Sie werden angehalten, wenn Sie unter brechbaren Code erreichen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [RuntimeSuspendAborted-Methode](icorprofilercallback-runtimesuspendaborted-method.md)
- [RuntimeSuspendFinished-Methode](icorprofilercallback-runtimesuspendfinished-method.md)
