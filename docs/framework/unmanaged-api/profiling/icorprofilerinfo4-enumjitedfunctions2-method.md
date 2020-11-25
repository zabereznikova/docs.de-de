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
ms.openlocfilehash: 2a6ddaef7b64427f8349abedbbd85b4d82a0b88c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697791"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>ICorProfilerInfo4::EnumJITedFunctions2-Methode

Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden. Diese Methode ersetzt die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die keine JIT-neu kompilierten IDs aufzählt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppEnum`  
 vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](icorprofilerfunctionenum-interface.md) -Enumerator.  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode überschneidet sich möglicherweise mit Rückrufen, `JITCompilation` wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Methode. Die zurückgegebene Enumeration enthält Werte für das `COR_PRF_FUNCTION::reJitId` Feld. Die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die von dieser Methode ersetzt wird, listet keine erneut JIT-kompilierten IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld immer auf 0 festgelegt ist. Die `ICorProfilerInfo4::EnumJITedFunctions` -Methode listet JIT-kompilierte IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld ordnungsgemäß festgelegt ist. Beachten Sie, dass die [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode eine Garbage Collection auslöst, während die [ICorProfilerInfo3:: EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md) dies nicht tun kann.  Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md)
- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
