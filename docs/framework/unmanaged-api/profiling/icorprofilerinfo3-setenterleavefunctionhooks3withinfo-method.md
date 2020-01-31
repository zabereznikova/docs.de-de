---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: 4fe18b4f07e6f282571b13faff5ce51b66ce416b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868485"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a>ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode
Gibt die vom Profiler implementierten Funktionen an, die für die [FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Hooks von verwalteten Funktionen aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>Parameters  
 `pFuncEnter3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionEnter3WithInfo` Rückruf verwendet werden soll.  
  
 `pFuncLeave3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionLeave3WithInfo` Rückruf verwendet werden soll.  
  
 `pFuncTailcall3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionTailcall3WithInfo` Rückruf verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die Hooks [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) stellen Stapel Rahmen und Argument Untersuchung bereit. Um auf diese Informationen zuzugreifen, müssen die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen, und dann die `SetEnterLeaveFunctionHooks3WithInfo`-Methode verwenden, um die Implementierung dieser Funktion zu registrieren.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein, und die neueste Version hat Vorrang. Wenn ein Profiler sowohl [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) als auch `SetEnterLeaveFunctionHooks3WithInfo`aufruft, wird daher `SetEnterLeaveFunctionHooks3WithInfo` verwendet.  
  
 Die `SetEnterLeaveFunctionHooks3WithInfo`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
