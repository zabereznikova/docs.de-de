---
title: ICorProfilerCallback::RuntimeThreadResumed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
ms.openlocfilehash: d3949189a72583ebb50b67a270694a31f1eb23dc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503210"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a>ICorProfilerCallback::RuntimeThreadResumed-Methode
Benachrichtigt den Profiler, dass der angegebene Thread nach dem aussetzen fortgesetzt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadId`  
 in Die ID des Threads, der fortgesetzt wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [RuntimeThreadSuspended-Methode](icorprofilercallback-runtimethreadsuspended-method.md)
