---
title: Profilerstellung für globale statische Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 1b0ad42e6b34e99212e112f6a594b0a36b6715e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723076"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="d1f54-102">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="d1f54-102">Profiling Global Static Functions</span></span>

<span data-ttu-id="d1f54-103">In diesem Abschnitt werden die von der Profilerstellungs-API verwendeten nicht verwalteten API-Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1f54-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1f54-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d1f54-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="d1f54-105">Profil Erstellungs Funktionen der .NET Framework Version 1</span><span class="sxs-lookup"><span data-stu-id="d1f54-105">.NET Framework version 1 Profiling Functions</span></span>  

 [<span data-ttu-id="d1f54-106">FunctionEnter-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="d1f54-107">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="d1f54-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="d1f54-108">Veraltet in .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d1f54-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="d1f54-109">FunctionLeave-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="d1f54-110">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d1f54-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="d1f54-111">Veraltet in .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d1f54-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="d1f54-112">FunctionTailcall-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="d1f54-113">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1f54-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="d1f54-114">Veraltet in .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d1f54-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="d1f54-115">Profil Erstellungs Funktionen der .NET Framework Version 2</span><span class="sxs-lookup"><span data-stu-id="d1f54-115">.NET Framework version 2 Profiling Functions</span></span>  

 [<span data-ttu-id="d1f54-116">FunctionIDMapper-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="d1f54-117">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](functionenter2-function.md)-, [FunctionLeave2](functionleave2-function.md)-und [FunctionTailcall2](functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1f54-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="d1f54-118">Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="d1f54-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="d1f54-119">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="d1f54-120">Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt Informationen über den Stapel Rahmen und die Funktionsargumente bereit.</span><span class="sxs-lookup"><span data-stu-id="d1f54-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="d1f54-121">In der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d1f54-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d1f54-122">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="d1f54-123">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit.</span><span class="sxs-lookup"><span data-stu-id="d1f54-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="d1f54-124">In der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d1f54-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d1f54-125">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="d1f54-126">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d1f54-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="d1f54-127">In der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d1f54-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="d1f54-128">StackSnapshotCallback-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="d1f54-129">Stellt dem Profiler Informationen über jeden verwalteten Frame und jede ausführen nicht verwalteter Frames auf dem Stapel während eines Stackwalk bereit, der von der [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="d1f54-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="d1f54-130">Profil Erstellungs Funktionen der .NET Framework Version 4</span><span class="sxs-lookup"><span data-stu-id="d1f54-130">.NET Framework version 4 Profiling Functions</span></span>  

 [<span data-ttu-id="d1f54-131">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="d1f54-132">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter3](functionenter3-function.md)-, [FunctionLeave3](functionleave3-function.md)-und [FunctionTailcall3](functiontailcall3-function.md)-und[FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Rückrufe für diese Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1f54-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="d1f54-133">Ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="d1f54-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="d1f54-134">`FunctionIDMapper2` erweitert die [FunctionIDMapper](functionidmapper-function.md) -Funktion mit einem `clientData` Parameter, den Profiler verwenden können, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d1f54-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="d1f54-135">FunctionEnter3-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="d1f54-136">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="d1f54-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="d1f54-137">FunctionEnter3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="d1f54-138">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen des Stapel Rahmens und der Funktionsargumente übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1f54-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="d1f54-139">FunctionLeave3-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="d1f54-140">Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d1f54-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="d1f54-141">FunctionLeave3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="d1f54-142">Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) zum Abrufen des Stapel Rahmens und des Rückgabewerts übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1f54-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="d1f54-143">FunctionTailcall3-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="d1f54-144">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1f54-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="d1f54-145">FunctionTailcall3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1f54-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="d1f54-146">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Tail-Aufruf einer anderen Funktion ausführt, und stellt ein Handle bereit, das an [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapel Rahmens übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1f54-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1f54-147">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d1f54-147">Related Sections</span></span>  

 [<span data-ttu-id="d1f54-148">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="d1f54-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="d1f54-149">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1f54-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="d1f54-150">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="d1f54-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="d1f54-151">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d1f54-151">Profiling Structures</span></span>](profiling-structures.md)
