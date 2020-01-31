---
title: ICorProfilerCallback::RuntimeThreadSuspended-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865869"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended-Methode
Benachrichtigt den Profiler, dass der angegebene Thread angehalten wurde oder im Begriff ist, angehalten zu werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Parameters  
 `threadId`  
 in Die ID des Threads, der angehalten wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die `RuntimeThreadSuspended` Benachrichtigung kann jederzeit zwischen der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -und der zugeordneten [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) -Rückrufe auftreten. Benachrichtigungen zwischen [ICorProfilerCallback:: runtimesuspendend](icorprofilercallback-runtimesuspendfinished-method.md) und `RuntimeResumeStarted` gelten für Threads, die in nicht verwaltetem Code ausgeführt wurden und bei einem Eintrag zur Laufzeit angehalten wurden.  
  
 Dieser Rückruf tritt im Allgemeinen auf, wenn ein Thread angehalten wird. Wenn jedoch der derzeit ausgeführte Thread (der Thread, der diesen Rückruf aufgerufen hat) der Vorgang ist, der angehalten wird, wird dieser Rückruf unmittelbar vor dem Aussetzen des Threads ausgeführt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [RuntimeThreadResumed-Methode](icorprofilercallback-runtimethreadresumed-method.md)
