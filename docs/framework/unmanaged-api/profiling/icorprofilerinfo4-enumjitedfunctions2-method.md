---
title: ICorProfilerInfo4::EnumJITedFunctions2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 3903ebf1ad35bd7eb1ba49b4f1acda9024678423
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862203"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>ICorProfilerInfo4::EnumJITedFunctions2-Methode
Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden. Diese Methode ersetzt die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die keine JIT-neu kompilierten IDs aufzählt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppEnum`  
 vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](icorprofilerfunctionenum-interface.md) -Enumerator.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode überschneidet sich möglicherweise mit `JITCompilation` Rückrufen wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Methode. Die zurückgegebene Enumeration enthält Werte für das Feld `COR_PRF_FUNCTION::reJitId`. Die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die von dieser Methode ersetzt wird, listet keine erneut JIT-kompilierten IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld immer auf 0 festgelegt ist. Die `ICorProfilerInfo4::EnumJITedFunctions`-Methode listet JIT-kompilierte IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld ordnungsgemäß festgelegt ist. Beachten Sie, dass die [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode eine Garbage Collection auslöst, während die [ICorProfilerInfo3:: EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md) dies nicht tun kann.  Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md)
- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
