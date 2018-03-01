---
title: FunctionLeave-Funktion
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
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14b8c1c5d36178e672bee363a192cd4eae435467
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave-function"></a><span data-ttu-id="ce9e8-102">FunctionLeave-Funktion</span><span class="sxs-lookup"><span data-stu-id="ce9e8-102">FunctionLeave Function</span></span>
<span data-ttu-id="ce9e8-103">Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce9e8-104">Die `FunctionLeave` -Funktion ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="ce9e8-105">Es sind weiterhin funktionsfähig, jedoch eine Leistungseinbuße entstehen.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ce9e8-106">Verwenden der [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) stattdessen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9e8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce9e8-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce9e8-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce9e8-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ce9e8-109">[in] Der Bezeichner der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce9e8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce9e8-110">Remarks</span></span>  
 <span data-ttu-id="ce9e8-111">Die `FunctionLeave` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="ce9e8-112">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ce9e8-113">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ce9e8-114">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="ce9e8-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ce9e8-115">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ce9e8-116">Die Implementierung der `FunctionLeave` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ce9e8-117">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ce9e8-118">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="ce9e8-119">Darüber hinaus die `FunctionLeave` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="ce9e8-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce9e8-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce9e8-120">Requirements</span></span>  
 <span data-ttu-id="ce9e8-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce9e8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce9e8-122">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ce9e8-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ce9e8-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce9e8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce9e8-124">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ce9e8-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9e8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce9e8-125">See Also</span></span>  
 [<span data-ttu-id="ce9e8-126">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ce9e8-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="ce9e8-127">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ce9e8-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="ce9e8-128">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ce9e8-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="ce9e8-129">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="ce9e8-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="ce9e8-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ce9e8-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
