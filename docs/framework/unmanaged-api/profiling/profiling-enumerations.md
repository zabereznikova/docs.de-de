---
title: Profilerstellungsenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447450"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="b3c8f-102">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="b3c8f-102">Profiling Enumerations</span></span>
<span data-ttu-id="b3c8f-103">Dieser Abschnitt beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3c8f-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b3c8f-104">In This Section</span></span>  
 [<span data-ttu-id="b3c8f-105">COR_PRF_CLAUSE_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="b3c8f-106">Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="b3c8f-107">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="b3c8f-108">Definiert die Codegenerierungs-Flags, die mit der [icorprofilerfunctioncontrol:: setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="b3c8f-109">COR_PRF_FINALIZER_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="b3c8f-110">Beschreibt den Finalizer für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="b3c8f-111">COR_PRF_GC_GENERATION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-111">COR_PRF_GC_GENERATION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="b3c8f-112">Identifiziert die Erstellung der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="b3c8f-113">COR_PRF_GC_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-113">COR_PRF_GC_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="b3c8f-114">Zeigt den Grund, weshalb die Garbage Collection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="b3c8f-115">COR_PRF_GC_ROOT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="b3c8f-116">Zeigt die Eigenschaften eines Garbage Collector-Stamms.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="b3c8f-117">COR_PRF_GC_ROOT_KIND-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="b3c8f-118">Gibt die Art des Garbage Collector Stamms an, der durch den Rückruf " [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) " verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="b3c8f-119">COR_PRF_HIGH_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="b3c8f-120">Bietet zusätzlich zu den in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gefundenen Flags, die der Profiler beim Laden an die [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode angeben kann.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="b3c8f-121">COR_PRF_JIT_CACHE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-121">COR_PRF_JIT_CACHE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="b3c8f-122">Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="b3c8f-123">COR_PRF_MISC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-123">COR_PRF_MISC Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 <span data-ttu-id="b3c8f-124">Enthält Konstantenwerte, die spezielle Bezeichner angeben.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="b3c8f-125">COR_PRF_MODULE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="b3c8f-126">Gibt die Eigenschaften eines Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="b3c8f-127">COR_PRF_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="b3c8f-128">Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="b3c8f-129">COR_PRF_RUNTIME_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="b3c8f-130">Enthält Werte, die die Version der Common Language Runtime angeben.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="b3c8f-131">COR_PRF_SNAPSHOT_INFO-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="b3c8f-132">Gibt an, wie viele Daten in jedem Aufruf an die `StackSnapshotCallback`-Funktion des Profilers an eine Stapelmomentaufnahmeme zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="b3c8f-133">COR_PRF_STATIC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="b3c8f-134">Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="b3c8f-135">COR_PRF_SUSPEND_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="b3c8f-136">Zeigt den Grund an, aus dem die Laufzeit angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="b3c8f-137">COR_PRF_TRANSITION_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3c8f-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="b3c8f-138">Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3c8f-139">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b3c8f-139">Related Sections</span></span>  
 [<span data-ttu-id="b3c8f-140">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b3c8f-140">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="b3c8f-141">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b3c8f-141">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="b3c8f-142">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="b3c8f-142">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="b3c8f-143">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="b3c8f-143">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
