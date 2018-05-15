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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58e7b3e76d90e9e43f3f5259c52b52cd9f8e1f6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="83ba4-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode</span><span class="sxs-lookup"><span data-stu-id="83ba4-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="83ba4-103">Gibt Profiler implementierten Funktionen an, die für "eingeben", "Übernehmen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83ba4-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ba4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83ba4-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83ba4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83ba4-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="83ba4-106">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="83ba4-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="83ba4-107">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="83ba4-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="83ba4-108">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="83ba4-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83ba4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83ba4-109">Remarks</span></span>  
 <span data-ttu-id="83ba4-110">In .NET Framework, Version 1.0 kann jeder Funktionszeiger So deaktivieren Sie die entsprechenden Rückruffunktion null sein.</span><span class="sxs-lookup"><span data-stu-id="83ba4-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="83ba4-111">Nur ein Satz von Rückrufen kann zu einem Zeitpunkt aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="83ba4-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="83ba4-112">Daher, wenn ein Profiler beide ruft `SetEnterLeaveFunctionHooks` und [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), klicken Sie dann `SetEnterLeaveFunctionHooks2` hat Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="83ba4-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="83ba4-113">Die `SetEnterLeaveFunctionHooks` Methode kann aufgerufen werden, nur von des Profilers [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="83ba4-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ba4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83ba4-114">Requirements</span></span>  
 <span data-ttu-id="83ba4-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83ba4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83ba4-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83ba4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83ba4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83ba4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83ba4-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83ba4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ba4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83ba4-119">See Also</span></span>  
 [<span data-ttu-id="83ba4-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83ba4-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
