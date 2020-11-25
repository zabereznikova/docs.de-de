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
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="887bd-102">ICorProfilerInfo4::EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="887bd-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>

<span data-ttu-id="887bd-103">Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="887bd-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="887bd-104">Diese Methode ersetzt die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die keine JIT-neu kompilierten IDs aufzählt.</span><span class="sxs-lookup"><span data-stu-id="887bd-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="887bd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="887bd-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="887bd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="887bd-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="887bd-107">vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](icorprofilerfunctionenum-interface.md) -Enumerator.</span><span class="sxs-lookup"><span data-stu-id="887bd-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="887bd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="887bd-108">Remarks</span></span>  

 <span data-ttu-id="887bd-109">Diese Methode überschneidet sich möglicherweise mit Rückrufen, `JITCompilation` wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="887bd-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="887bd-110">Die zurückgegebene Enumeration enthält Werte für das `COR_PRF_FUNCTION::reJitId` Feld.</span><span class="sxs-lookup"><span data-stu-id="887bd-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="887bd-111">Die [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die von dieser Methode ersetzt wird, listet keine erneut JIT-kompilierten IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld immer auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="887bd-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="887bd-112">Die `ICorProfilerInfo4::EnumJITedFunctions` -Methode listet JIT-kompilierte IDs auf, da das `COR_PRF_FUNCTION::reJitId` Feld ordnungsgemäß festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="887bd-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="887bd-113">Beachten Sie, dass die [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode eine Garbage Collection auslöst, während die [ICorProfilerInfo3:: EnumJITedFunctions-Methode](icorprofilerinfo3-enumjitedfunctions-method.md) dies nicht tun kann.</span><span class="sxs-lookup"><span data-stu-id="887bd-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="887bd-114">Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="887bd-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="887bd-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="887bd-115">Requirements</span></span>  

 <span data-ttu-id="887bd-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="887bd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="887bd-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="887bd-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="887bd-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="887bd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="887bd-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="887bd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887bd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="887bd-120">See also</span></span>

- [<span data-ttu-id="887bd-121">EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="887bd-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="887bd-122">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="887bd-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="887bd-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="887bd-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="887bd-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="887bd-124">Profiling</span></span>](index.md)
