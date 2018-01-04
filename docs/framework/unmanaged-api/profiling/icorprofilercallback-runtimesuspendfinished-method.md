---
title: ICorProfilerCallback::RuntimeSuspendFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6127d0c5f3b193dad1586cdaf92beb8d8734376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished-Methode
Benachrichtigt den Profiler, dass die Common Language Runtime Anhalten des Threads für alle Common Language Runtime abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind dürfen weiter ausgeführt wird, bis sie versuchen, auf die Common Language Runtime erneut eingeben. An diesem Punkt werden sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die die Common Language Runtime eingeben. Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie bereits im Code parallelisiert sind oder sie aufgefordert werden, angehalten, wenn sie unterbrechbaren Code erreichen.  
  
 Die `RuntimeSuspendFinished` ist gewährleistet, dass Rückruf auftreten, auf dem gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
