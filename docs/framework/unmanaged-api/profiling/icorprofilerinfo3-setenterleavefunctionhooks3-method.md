---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77a2e8170cd2cf78576b2d376fb592c903bbb403
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a>ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
Gibt an, die vom Profiler implementierten Funktionen, die aufgerufen werden, auf die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFuncEnter3`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionEnter3` Rückruf.  
  
 `pFuncLeave3`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionLeave3` Rückruf.  
  
 `pFuncTailcall3`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionTailcall3` Rückruf.  
  
## <a name="remarks"></a>Hinweise  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) Hooks bieten keine Stapel und Überprüfung. Zugriff auf diese Informationen, die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden müssen. Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode die Ereignisflags festlegen und dann mithilfe der [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) Methode zum Registrieren Ihrer die Implementierung dieser Funktion.  
  
 Nur ein Satz von Rückrufen möglicherweise zu einem Zeitpunkt aktiv sein, und die neueste Version Vorrang. Deshalb, wenn ein Profiler sowohl Ruft die [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) und die `SetEnterLeaveFunctionHooks3` -Methode, `SetEnterLeaveFunctionHooks3` verwendet wird.  
  
 Die `SetEnterLeaveFunctionHooks3` -Methode aufgerufen werden kann, nur von des Profilers [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 [ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
