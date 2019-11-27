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
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446965"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished-Methode
Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads angehalten hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben. An diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die zur Laufzeit gelangen. Alle Threads in der Laufzeit werden entweder sofort angehalten, wenn Sie sich bereits in interruptebarem Code befinden, oder Sie werden angehalten, wenn Sie unter brechbaren Code erreichen.  
  
 Der `RuntimeSuspendFinished` Rückruf ist garantiert im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
