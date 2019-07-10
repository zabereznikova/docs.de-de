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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9279e50630ea074b70955ca8ed218cd39a613b58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781290"
---
# <a name="functionenter-function"></a><span data-ttu-id="5b428-102">FunctionEnter-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b428-102">FunctionEnter Function</span></span>
<span data-ttu-id="5b428-103">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5b428-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b428-104">Die `FunctionEnter` Funktion ist in .NET Framework, Version 2.0, veraltet und dessen Verwendung fallen die Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="5b428-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="5b428-105">Verwenden der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="5b428-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b428-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b428-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b428-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b428-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="5b428-108">[in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5b428-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b428-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b428-109">Remarks</span></span>  
 <span data-ttu-id="5b428-110">Die `FunctionEnter` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="5b428-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="5b428-111">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="5b428-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="5b428-112">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b428-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5b428-113">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="5b428-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5b428-114">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="5b428-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5b428-115">Die Implementierung der `FunctionEnter` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="5b428-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="5b428-116">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="5b428-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5b428-117">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5b428-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="5b428-118">Darüber hinaus die `FunctionEnter` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="5b428-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b428-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b428-119">Requirements</span></span>  
 <span data-ttu-id="5b428-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b428-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b428-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5b428-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5b428-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b428-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b428-123">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="5b428-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b428-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b428-124">See also</span></span>

- [<span data-ttu-id="5b428-125">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b428-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="5b428-126">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b428-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="5b428-127">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b428-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="5b428-128">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="5b428-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="5b428-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5b428-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
