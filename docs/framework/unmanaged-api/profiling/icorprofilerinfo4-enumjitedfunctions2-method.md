---
title: ICorProfilerInfo4::EnumJITedFunctions2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7dc381848307ea0606f6989d6946c11aa5ef9a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="18b7e-102">ICorProfilerInfo4::EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="18b7e-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="18b7e-103">Gibt einen Enumerator für alle Funktionen, die bereits JIT-kompiliert und JIT-kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="18b7e-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="18b7e-104">Diese Methode ersetzt die [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die nicht erneut JIT-kompilierten IDs aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="18b7e-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b7e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="18b7e-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18b7e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="18b7e-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="18b7e-107">[out] Ein Zeiger auf die [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Enumerator.</span><span class="sxs-lookup"><span data-stu-id="18b7e-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18b7e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18b7e-108">Remarks</span></span>  
 <span data-ttu-id="18b7e-109">Diese Methode möglicherweise überschneiden sich mit `JITCompilation` Rückrufe, z. B. die [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="18b7e-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="18b7e-110">Die zurückgegebene-Enumeration enthält Werte für die `COR_PRF_FUNCTION::reJitId` Feld.</span><span class="sxs-lookup"><span data-stu-id="18b7e-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="18b7e-111">Die [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) -Methode, die diese Methode ersetzt wird, nicht erneut JIT-kompilierten IDs aufgelistet, da die `COR_PRF_FUNCTION::reJitId` Feld immer auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18b7e-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="18b7e-112">Die `ICorProfilerInfo4::EnumJITedFunctions` Methode JIT-kompilierten-IDs aufgelistet werden, da die `COR_PRF_FUNCTION::reJitId` Feld ordnungsgemäß festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18b7e-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="18b7e-113">Beachten Sie, dass die [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) Methode kann eine Garbagecollection auslösen, wohingegen [ICorProfilerInfo3:: EnumJITedFunctions-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) geschieht dies nicht.</span><span class="sxs-lookup"><span data-stu-id="18b7e-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="18b7e-114">Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="18b7e-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18b7e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18b7e-115">Requirements</span></span>  
 <span data-ttu-id="18b7e-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b7e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b7e-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18b7e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18b7e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18b7e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18b7e-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b7e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b7e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18b7e-120">See Also</span></span>  
 [<span data-ttu-id="18b7e-121">EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="18b7e-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)  
 [<span data-ttu-id="18b7e-122">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18b7e-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="18b7e-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="18b7e-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="18b7e-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="18b7e-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
