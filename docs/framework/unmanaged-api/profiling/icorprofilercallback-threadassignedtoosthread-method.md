---
title: ICorProfilerCallback::ThreadAssignedToOSThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 1b69c0522c47d4e675180af67adab166626da4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440024"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a>ICorProfilerCallback::ThreadAssignedToOSThread-Methode
Benachrichtigt den Profiler, dass ein verwalteter Thread mithilfe eines bestimmten Betriebssystem Threads implementiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a>Parameter  
 `managedThreadId`  
 in Der Bezeichner des verwalteten Threads.  
  
 `osThreadId`  
 in Der Bezeichner des Betriebssystem Threads.  
  
## <a name="remarks"></a>Hinweise  
 Der `ThreadAssignedToOSThread` Rückruf ist vorhanden, sodass der Profiler eine genaue Zuordnung zwischen Fibers von Betriebssystemthreads und verwalteten Threads aufrechterhalten kann.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
