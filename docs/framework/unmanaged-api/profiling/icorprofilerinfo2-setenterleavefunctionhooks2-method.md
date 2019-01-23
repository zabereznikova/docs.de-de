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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb7c8fa40d260e45ae536f1b58c6ab360f35448e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550642"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="4e779-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="4e779-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="4e779-103">Gibt an, Profiler implementierten Funktionen an, für die aktualisierten Versionen der "eingeben", "verlassen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4e779-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e779-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e779-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e779-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e779-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="4e779-106">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4e779-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="4e779-107">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4e779-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="4e779-108">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4e779-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e779-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e779-109">Remarks</span></span>  
 <span data-ttu-id="4e779-110">Die `SetEnterLeaveFunctionHooks2` Methode ähnelt der [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="4e779-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="4e779-111">Verwenden Sie Ersteres an Funktionen, wie die höheren Versionen die Enter/Leave/Tailcall-Rückrufe und die zweite verwendet werden, an die Funktionen als die älteren Versionen der Enter/Leave/Tailcall Rückrufe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e779-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="4e779-112">Nur einen Satz von Rückrufen kann jeweils aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="4e779-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="4e779-113">Also, wenn ein Profiler aufruft `ICorProfilerInfo::SetEnterLeaveFunctionHooks` und `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e779-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="4e779-114">Die `SetEnterLeaveFunctionHooks2` Methode aufgerufen werden kann, nur über die Profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4e779-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e779-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e779-115">Requirements</span></span>  
 <span data-ttu-id="4e779-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e779-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e779-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e779-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e779-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e779-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e779-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e779-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e779-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e779-120">See also</span></span>
- [<span data-ttu-id="4e779-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e779-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4e779-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e779-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
