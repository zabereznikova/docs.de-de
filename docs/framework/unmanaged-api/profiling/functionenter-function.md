---
title: FunctionEnter-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: ad34592223433f0bf541c390674bcf96839b6ca8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440818"
---
# <a name="functionenter-function"></a><span data-ttu-id="7987f-102">FunctionEnter-Funktion</span><span class="sxs-lookup"><span data-stu-id="7987f-102">FunctionEnter Function</span></span>
<span data-ttu-id="7987f-103">Notifies the profiler that control is being passed to a function.</span><span class="sxs-lookup"><span data-stu-id="7987f-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7987f-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span><span class="sxs-lookup"><span data-stu-id="7987f-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="7987f-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span><span class="sxs-lookup"><span data-stu-id="7987f-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7987f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7987f-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7987f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7987f-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="7987f-108">[in] The identifier of the function to which control is passed.</span><span class="sxs-lookup"><span data-stu-id="7987f-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7987f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7987f-109">Remarks</span></span>  
 <span data-ttu-id="7987f-110">The `FunctionEnter` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="7987f-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="7987f-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="7987f-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="7987f-112">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="7987f-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="7987f-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="7987f-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="7987f-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="7987f-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7987f-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7987f-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="7987f-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="7987f-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7987f-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span><span class="sxs-lookup"><span data-stu-id="7987f-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="7987f-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span><span class="sxs-lookup"><span data-stu-id="7987f-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7987f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7987f-119">Requirements</span></span>  
 <span data-ttu-id="7987f-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7987f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7987f-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7987f-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7987f-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7987f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7987f-123">**.NET Framework Versions:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="7987f-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7987f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7987f-124">See also</span></span>

- [<span data-ttu-id="7987f-125">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7987f-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="7987f-126">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7987f-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="7987f-127">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7987f-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="7987f-128">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="7987f-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="7987f-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="7987f-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
