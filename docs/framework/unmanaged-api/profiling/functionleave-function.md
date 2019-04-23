---
title: FunctionLeave-Funktion
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b1fe219c4c852792390b48b0ea4d38adb702281
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218887"
---
# <a name="functionleave-function"></a><span data-ttu-id="451ac-102">FunctionLeave-Funktion</span><span class="sxs-lookup"><span data-stu-id="451ac-102">FunctionLeave Function</span></span>
<span data-ttu-id="451ac-103">Benachrichtigt den Profiler, dass eine Funktion zum an den Aufrufer zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="451ac-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="451ac-104">Die `FunctionLeave` Funktion ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="451ac-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="451ac-105">Diese Funktion bleibt weiterhin funktioniert, jedoch eine Leistungseinbuße fallen.</span><span class="sxs-lookup"><span data-stu-id="451ac-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="451ac-106">Verwenden der [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="451ac-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451ac-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="451ac-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="451ac-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="451ac-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="451ac-109">[in] Der Bezeichner der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="451ac-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="451ac-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="451ac-110">Remarks</span></span>  
 <span data-ttu-id="451ac-111">Die `FunctionLeave` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="451ac-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="451ac-112">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="451ac-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="451ac-113">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="451ac-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="451ac-114">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="451ac-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="451ac-115">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="451ac-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="451ac-116">Die Implementierung der `FunctionLeave` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="451ac-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="451ac-117">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="451ac-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="451ac-118">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="451ac-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="451ac-119">Darüber hinaus die `FunctionLeave` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="451ac-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="451ac-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="451ac-120">Requirements</span></span>  
 <span data-ttu-id="451ac-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451ac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="451ac-122">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="451ac-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="451ac-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="451ac-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="451ac-124">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="451ac-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451ac-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="451ac-125">See also</span></span>

- [<span data-ttu-id="451ac-126">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="451ac-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="451ac-127">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="451ac-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="451ac-128">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="451ac-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="451ac-129">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="451ac-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="451ac-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="451ac-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
