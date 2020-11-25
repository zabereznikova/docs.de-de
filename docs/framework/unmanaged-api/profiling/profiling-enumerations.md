---
title: Profilerstellungsenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 8956a09cf76aa54452e8c020239e650e55d8a0d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701613"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="c9fed-102">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="c9fed-102">Profiling Enumerations</span></span>

<span data-ttu-id="c9fed-103">Dieser Abschnitt beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9fed-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9fed-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c9fed-104">In This Section</span></span>  

 [<span data-ttu-id="c9fed-105">COR_PRF_CLAUSE_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="c9fed-106">Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.</span><span class="sxs-lookup"><span data-stu-id="c9fed-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="c9fed-107">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="c9fed-108">Definiert die Codegenerierungs-Flags, die mit der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="c9fed-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="c9fed-109">COR_PRF_FINALIZER_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="c9fed-110">Beschreibt den Finalizer für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9fed-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="c9fed-111">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-111">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="c9fed-112">Identifiziert die Erstellung der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c9fed-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="c9fed-113">COR_PRF_GC_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-113">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="c9fed-114">Zeigt den Grund, weshalb die Garbage Collection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="c9fed-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="c9fed-115">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="c9fed-116">Zeigt die Eigenschaften eines Garbage Collector-Stamms.</span><span class="sxs-lookup"><span data-stu-id="c9fed-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="c9fed-117">COR_PRF_GC_ROOT_KIND-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="c9fed-118">Gibt die Art des Garbage Collector Stamms an, der durch den Rückruf " [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) " verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c9fed-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="c9fed-119">COR_PRF_HIGH_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="c9fed-120">Bietet zusätzlich zu den in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) Enumeration gefundenen Flags, die der Profiler beim Laden an die [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode angeben kann.</span><span class="sxs-lookup"><span data-stu-id="c9fed-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="c9fed-121">COR_PRF_JIT_CACHE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-121">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="c9fed-122">Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.</span><span class="sxs-lookup"><span data-stu-id="c9fed-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="c9fed-123">COR_PRF_MISC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-123">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="c9fed-124">Enthält Konstantenwerte, die spezielle Bezeichner angeben.</span><span class="sxs-lookup"><span data-stu-id="c9fed-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="c9fed-125">COR_PRF_MODULE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="c9fed-126">Gibt die Eigenschaften eines Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c9fed-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="c9fed-127">COR_PRF_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-127">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="c9fed-128">Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.</span><span class="sxs-lookup"><span data-stu-id="c9fed-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="c9fed-129">COR_PRF_RUNTIME_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="c9fed-130">Enthält Werte, die die Version der Common Language Runtime angeben.</span><span class="sxs-lookup"><span data-stu-id="c9fed-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="c9fed-131">COR_PRF_SNAPSHOT_INFO-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="c9fed-132">Gibt an, wie viele Daten in jedem Aufruf an die `StackSnapshotCallback`-Funktion des Profilers an eine Stapelmomentaufnahmeme zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9fed-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="c9fed-133">COR_PRF_STATIC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="c9fed-134">Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="c9fed-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="c9fed-135">COR_PRF_SUSPEND_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="c9fed-136">Zeigt den Grund an, aus dem die Laufzeit angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="c9fed-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="c9fed-137">COR_PRF_TRANSITION_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c9fed-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="c9fed-138">Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="c9fed-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9fed-139">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c9fed-139">Related Sections</span></span>  

 [<span data-ttu-id="c9fed-140">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c9fed-140">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="c9fed-141">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c9fed-141">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="c9fed-142">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="c9fed-142">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="c9fed-143">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="c9fed-143">Profiling Structures</span></span>](profiling-structures.md)
