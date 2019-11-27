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
ms.openlocfilehash: 45593e7e30e1c8f8036489936aab3c607b01dd52
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438650"
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
 in Ein Zeiger auf die-Implementierung, die als [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncLeave`  
 in Ein Zeiger auf die-Implementierung, die als [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) -Rückruf verwendet werden soll.  
  
 `pFuncTailcall`  
 in Ein Zeiger auf die-Implementierung, die als [functiontailcallrückruf](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework Version 1,0 kann jeder Funktionszeiger NULL sein, um den entsprechenden Rückruf zu deaktivieren.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein. Wenn ein Profiler sowohl `SetEnterLeaveFunctionHooks` als auch [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)aufruft, hat `SetEnterLeaveFunctionHooks2` Vorrang.  
  
 Die `SetEnterLeaveFunctionHooks`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
