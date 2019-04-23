---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f95a404ce7124a76ee527cdc70ccccf103838b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076795"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode
Gibt an, Profiler implementierten Funktionen an, für die aktualisierten Versionen der "eingeben", "verlassen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFuncEnter`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) Rückruf.  
  
 `pFuncLeave`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf.  
  
 `pFuncTailcall`  
 [in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückruf.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetEnterLeaveFunctionHooks2` Methode ähnelt der [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) Methode. Verwenden Sie Ersteres an Funktionen, wie die höheren Versionen die Enter/Leave/Tailcall-Rückrufe und die zweite verwendet werden, an die Funktionen als die älteren Versionen der Enter/Leave/Tailcall Rückrufe verwendet werden soll.  
  
 Nur einen Satz von Rückrufen kann jeweils aktiv sein. Also, wenn ein Profiler aufruft `ICorProfilerInfo::SetEnterLeaveFunctionHooks` und `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` wird verwendet.  
  
 Die `SetEnterLeaveFunctionHooks2` Methode aufgerufen werden kann, nur über die Profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
