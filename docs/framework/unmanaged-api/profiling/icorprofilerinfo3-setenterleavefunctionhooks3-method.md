---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: 3e07d2b61e85bb626613c40832c1a6aa499ef248
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868498"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a>ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
Gibt die vom Profiler implementierten Funktionen an, die für die Funktionen [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)und [FunctionTailcall3](functiontailcall3-function.md) aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>Parameters  
 `pFuncEnter3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionEnter3` Rückruf verwendet werden soll.  
  
 `pFuncLeave3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionLeave3` Rückruf verwendet werden soll.  
  
 `pFuncTailcall3`  
 in Ein Zeiger auf die-Implementierung, die als `FunctionTailcall3` Rückruf verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 [FunctionEnter3](functionenter3-function.md)-, [FunctionLeave3](functionleave3-function.md)-und [FunctionTailcall3](functiontailcall3-function.md) -Hooks bieten keine Stapel Rahmen-und Argument Untersuchung. Um auf diese Informationen zuzugreifen, müssen die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) -Methode verwenden, um die Implementierung dieser Funktion zu registrieren.  
  
 Es kann jeweils nur ein Satz von Rückrufen aktiv sein, und die neueste Version hat Vorrang. Wenn ein Profiler sowohl die [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) als auch die `SetEnterLeaveFunctionHooks3`-Methode aufruft, wird daher `SetEnterLeaveFunctionHooks3` verwendet.  
  
 Die `SetEnterLeaveFunctionHooks3`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
- [ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
