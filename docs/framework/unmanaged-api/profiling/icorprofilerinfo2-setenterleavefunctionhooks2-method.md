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
ms.openlocfilehash: 4068c8fee13a6086bc6b48bcc6d4117357062747
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449784"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode
Gibt vom Profiler implementierte Funktionen an, die für die aktualisierten Versionen der Hooks "Enter", "Leave" und "Tailcall" von verwalteten Funktionen aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFuncEnter`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncLeave`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncTailcall`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) -Rückruf verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetEnterLeaveFunctionHooks2`-Methode ähnelt der [ICorProfilerInfo:: abtenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) -Methode. Verwenden Sie das erste, um Funktionen anzugeben, die als neuere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen, und letztere zum Angeben von Funktionen, die als ältere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein. Wenn ein Profiler sowohl `ICorProfilerInfo::SetEnterLeaveFunctionHooks` als auch `SetEnterLeaveFunctionHooks2`aufruft, wird `SetEnterLeaveFunctionHooks2` verwendet.  
  
 Die `SetEnterLeaveFunctionHooks2`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
