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
ms.openlocfilehash: f7bc1954d11134a4515d2e29e9e0eb1626ae5d26
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863427"
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
  
## <a name="parameters"></a>Parameters  
 `pFuncEnter`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionEnter](functionenter-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncLeave`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionLeave](functionleave-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncTailcall`  
 in Ein Zeiger auf die-Implementierung, die als [functiontailcallrückruf](functiontailcall-function.md) verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework Version 1,0 kann jeder Funktionszeiger NULL sein, um den entsprechenden Rückruf zu deaktivieren.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein. Wenn ein Profiler sowohl `SetEnterLeaveFunctionHooks` als auch [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)aufruft, hat `SetEnterLeaveFunctionHooks2` Vorrang.  
  
 Die `SetEnterLeaveFunctionHooks`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
