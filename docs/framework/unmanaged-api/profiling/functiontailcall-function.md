---
title: FunctionTailcall-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall
helpviewer_keywords: FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 223f112ba405e29b800456adca2f83e0cef6e7b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall-function"></a><span data-ttu-id="79522-102">FunctionTailcall-Funktion</span><span class="sxs-lookup"><span data-stu-id="79522-102">FunctionTailcall Function</span></span>
<span data-ttu-id="79522-103">Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="79522-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79522-104">Die `FunctionTailcall` -Funktion ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="79522-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="79522-105">Es sind weiterhin funktionsfähig, jedoch eine Leistungseinbuße entstehen.</span><span class="sxs-lookup"><span data-stu-id="79522-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="79522-106">Verwenden der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) stattdessen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="79522-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79522-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="79522-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79522-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="79522-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="79522-109">[in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="79522-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79522-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79522-110">Remarks</span></span>  
 <span data-ttu-id="79522-111">Der Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen und direkt an den Aufrufer der Funktion, die den Endeaufruf vorgenommen zurück.</span><span class="sxs-lookup"><span data-stu-id="79522-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="79522-112">Dies bedeutet, dass eine [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ist ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="79522-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="79522-113">Die `FunctionTailcall` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="79522-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="79522-114">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="79522-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="79522-115">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="79522-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="79522-116">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="79522-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="79522-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="79522-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="79522-118">Die Implementierung der `FunctionTailcall` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="79522-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="79522-119">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="79522-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="79522-120">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="79522-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="79522-121">Darüber hinaus die `FunctionTailcall` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="79522-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79522-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79522-122">Requirements</span></span>  
 <span data-ttu-id="79522-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79522-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79522-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="79522-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="79522-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79522-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79522-126">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="79522-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79522-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79522-127">See Also</span></span>  
 [<span data-ttu-id="79522-128">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="79522-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="79522-129">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="79522-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="79522-130">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="79522-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="79522-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="79522-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
