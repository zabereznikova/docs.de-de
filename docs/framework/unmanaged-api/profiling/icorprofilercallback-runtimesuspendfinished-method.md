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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07e2ebe8afe6002dee6c45f56fa1f11a4083d6bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992133"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished-Methode
Benachrichtigt den Profiler an, die die Laufzeit Anhalten aller Threads der Common Language Runtime abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle Common Language Runtime-Threads, die in nicht verwaltetem Code können weiterhin ausgeführt, bis sie versuchen, auf die Runtime erneut eingeben. Sie werden an dieser Stelle auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die die Laufzeit eingeben. Alle Threads in der Laufzeit sind, dass entweder sofort angehalten, wenn sie bereits im unterbrechbaren Code, oder sie, zum Anhalten aufgefordert werden, wenn sie unterbrechbaren Code erreichen.  
  
 Die `RuntimeSuspendFinished` Rückruf wird garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
