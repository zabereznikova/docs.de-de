---
title: FunctionTailcall-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a38d4858d248ef4eefbcb9d97c13e68d9507fb12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665031"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="f1c19-102">FunctionTailcall-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1c19-102">FunctionTailcall Function</span></span>
<span data-ttu-id="f1c19-103">Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="f1c19-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1c19-104">Die `FunctionTailcall` Funktion ist in .NET Framework, Version 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="f1c19-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f1c19-105">Diese Funktion bleibt weiterhin funktioniert, jedoch eine Leistungseinbuße fallen.</span><span class="sxs-lookup"><span data-stu-id="f1c19-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="f1c19-106">Verwenden der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f1c19-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c19-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1c19-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1c19-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1c19-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="f1c19-109">[in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f1c19-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1c19-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1c19-110">Remarks</span></span>  
 <span data-ttu-id="f1c19-111">Die Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen, und es ergibt sich direkt an den Aufrufer der Funktion, die den Endeaufruf ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f1c19-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="f1c19-112">Dies bedeutet, dass eine [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1c19-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="f1c19-113">Die `FunctionTailcall` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="f1c19-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="f1c19-114">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="f1c19-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="f1c19-115">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="f1c19-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="f1c19-116">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="f1c19-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="f1c19-117">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="f1c19-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f1c19-118">Die Implementierung der `FunctionTailcall` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="f1c19-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="f1c19-119">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="f1c19-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f1c19-120">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f1c19-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="f1c19-121">Darüber hinaus die `FunctionTailcall` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="f1c19-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c19-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1c19-122">Requirements</span></span>  
 <span data-ttu-id="f1c19-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c19-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c19-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f1c19-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f1c19-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1c19-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1c19-126">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f1c19-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c19-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1c19-127">See also</span></span>
- [<span data-ttu-id="f1c19-128">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1c19-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="f1c19-129">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1c19-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="f1c19-130">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="f1c19-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="f1c19-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="f1c19-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
