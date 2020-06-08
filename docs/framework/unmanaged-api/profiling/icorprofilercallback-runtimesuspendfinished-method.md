---
title: ICorProfilerCallback::RuntimeSuspendFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 64611fa7368f05de906b71b08bda8f1e7c460bf3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503236"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished-Methode
Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads angehalten hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben. An diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die zur Laufzeit gelangen. Alle Threads in der Laufzeit werden entweder sofort angehalten, wenn Sie sich bereits in interruptebarem Code befinden, oder Sie werden angehalten, wenn Sie unter brechbaren Code erreichen.  
  
 Der `RuntimeSuspendFinished` Rückruf ist garantiert im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [RuntimeSuspendAborted-Methode](icorprofilercallback-runtimesuspendaborted-method.md)
