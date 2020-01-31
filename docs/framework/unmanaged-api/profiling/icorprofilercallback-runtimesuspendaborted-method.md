---
title: ICorProfilerCallback::RuntimeSuspendAborted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: 285bdd3f2a96d3c6cb0039382d9944e48c49971a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865908"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a>ICorProfilerCallback::RuntimeSuspendAborted-Methode
Benachrichtigt den Profiler, dass die Laufzeit das Eintreten der Lauf Zeit Unterbrechung abgebrochen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Lauf Zeit Unterbrechung kann abgebrochen werden, wenn zwei Threads gleichzeitig versuchen, die Laufzeit anzuhalten.  
  
 Entweder der Rückruf " [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendfinished-method.md) " oder der `RuntimeSuspendAborted` Rückruf erfolgt in einem einzelnen Thread nach einem [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf.  
  
 Der `RuntimeSuspendAborted` Rückruf ist garantiert im gleichen Thread wie der `RuntimeSuspendStarted` Rückruf.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
