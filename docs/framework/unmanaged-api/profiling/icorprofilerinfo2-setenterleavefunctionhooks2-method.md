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
ms.openlocfilehash: f71d0b5c77d4a514001bcbe6904ed912be388d18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681547"
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
 in Ein Zeiger auf die-Implementierung, die als [FunctionEnter2](functionenter2-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncLeave`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionLeave2](functionleave2-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncTailcall`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionTailcall2](functiontailcall2-function.md) -Rückruf verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  

 Die- `SetEnterLeaveFunctionHooks2` Methode ähnelt der [ICorProfilerInfo:: abtenterleavefunctionhooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) -Methode. Verwenden Sie das erste, um Funktionen anzugeben, die als neuere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen, und letztere zum Angeben von Funktionen, die als ältere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein. Wenn ein Profiler sowohl `ICorProfilerInfo::SetEnterLeaveFunctionHooks` als auch aufruft `SetEnterLeaveFunctionHooks2` , wird daher `SetEnterLeaveFunctionHooks2` verwendet.  
  
 Die `SetEnterLeaveFunctionHooks2` -Methode kann nur vom [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
