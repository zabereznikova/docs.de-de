---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 18aed5c5314fc1057767b599c538952a1d4d6b57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722231"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode

Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFuncEnter`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionEnter](functionenter-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncLeave`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionLeave](functionleave-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncTailcall`  
 in Ein Zeiger auf die-Implementierung, die als [functiontailcallrückruf](functiontailcall-function.md) verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  

 In der .NET Framework Version 1,0 kann jeder Funktionszeiger NULL sein, um den entsprechenden Rückruf zu deaktivieren.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein. Wenn ein Profiler sowohl `SetEnterLeaveFunctionHooks` als auch [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)aufruft, hat daher `SetEnterLeaveFunctionHooks2` Vorrang.  
  
 Die `SetEnterLeaveFunctionHooks` -Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
