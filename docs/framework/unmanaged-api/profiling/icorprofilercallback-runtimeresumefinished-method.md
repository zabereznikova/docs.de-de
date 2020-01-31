---
title: ICorProfilerCallback::RuntimeResumeFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 5cafbca75992a5fe8a7d3d95628e0018f1a2e8fa
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865947"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a>ICorProfilerCallback::RuntimeResumeFinished-Methode
Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortgesetzt hat und an den normalen Vorgang zurückgegeben wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Es ist nicht garantiert, dass der `RuntimeResumeFinished` Rückruf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf erfolgt. Es ist jedoch garantiert, dass Sie im gleichen Thread wie der [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) -Rückruf auftritt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
