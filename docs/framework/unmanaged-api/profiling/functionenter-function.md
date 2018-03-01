---
title: FunctionEnter-Funktion
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0387d6d5eee1c30cb1137072e2c4600f12479e8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter-function"></a><span data-ttu-id="47818-102">FunctionEnter-Funktion</span><span class="sxs-lookup"><span data-stu-id="47818-102">FunctionEnter Function</span></span>
<span data-ttu-id="47818-103">Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="47818-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47818-104">Die `FunctionEnter` -Funktion ist veraltet in .NET Framework, Version 2.0, und ihre Verwendung verursacht eine Leistungseinbuße.</span><span class="sxs-lookup"><span data-stu-id="47818-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="47818-105">Verwenden der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) stattdessen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="47818-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47818-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="47818-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47818-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="47818-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="47818-108">[in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="47818-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47818-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47818-109">Remarks</span></span>  
 <span data-ttu-id="47818-110">Die `FunctionEnter` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="47818-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="47818-111">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="47818-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="47818-112">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="47818-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="47818-113">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="47818-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="47818-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="47818-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="47818-115">Die Implementierung der `FunctionEnter` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="47818-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="47818-116">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="47818-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="47818-117">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47818-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="47818-118">Darüber hinaus die `FunctionEnter` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="47818-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47818-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47818-119">Requirements</span></span>  
 <span data-ttu-id="47818-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47818-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47818-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="47818-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="47818-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47818-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47818-123">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="47818-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47818-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47818-124">See Also</span></span>  
 [<span data-ttu-id="47818-125">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="47818-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="47818-126">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="47818-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="47818-127">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="47818-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="47818-128">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="47818-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="47818-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="47818-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
