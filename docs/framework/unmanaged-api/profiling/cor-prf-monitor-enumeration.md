---
title: COR_PRF_MONITOR-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 1ff167121a5bb752c70edd2c5901133503326bea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500805"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="411bf-102">COR_PRF_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="411bf-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="411bf-103">Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.</span><span class="sxs-lookup"><span data-stu-id="411bf-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="411bf-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="411bf-105">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-105">Members</span></span>  
 <span data-ttu-id="411bf-106">In den folgenden Abschnitten `COR_PRF_MONITOR` werden Enumerationsmember nach Kategorie aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="411bf-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="411bf-107">Die Kategorien lauten:</span><span class="sxs-lookup"><span data-stu-id="411bf-107">The categories are:</span></span>  
  
- [<span data-ttu-id="411bf-108">Keine Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="411bf-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="411bf-109">Rückruf-Flags</span><span class="sxs-lookup"><span data-stu-id="411bf-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="411bf-110">Flags zur Aktivierung von Funktionen</span><span class="sxs-lookup"><span data-stu-id="411bf-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="411bf-111">Konfigurationsflags</span><span class="sxs-lookup"><span data-stu-id="411bf-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="411bf-112">Kombinierte Flags</span><span class="sxs-lookup"><span data-stu-id="411bf-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a><span data-ttu-id="411bf-113">Keine Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="411bf-113">No flags set</span></span>  
  
|<span data-ttu-id="411bf-114">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-114">Member</span></span>|<span data-ttu-id="411bf-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411bf-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="411bf-116">Es sind keine Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="411bf-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a><span data-ttu-id="411bf-117">Rückruf-Flags</span><span class="sxs-lookup"><span data-stu-id="411bf-117">Callback flags</span></span>  
  
|<span data-ttu-id="411bf-118">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-118">Member</span></span>|<span data-ttu-id="411bf-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411bf-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="411bf-120">Aktiviert alle Rückrufereignisse.</span><span class="sxs-lookup"><span data-stu-id="411bf-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="411bf-121">Steuert die `AppDomainCreation*` `AppDomainShutdown*` Rückrufe und in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="411bf-122">Steuert die `AssemblyLoad*` `AssemblyUnload*` Rückrufe und in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="411bf-123">Steuert die `JITCachedFunctionSearch*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="411bf-124">Das Verhalten dieses Flags ändert sich in Version 2.0 von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="411bf-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="411bf-125">Steuert die `COMClassicVTable*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="411bf-126">Steuert die `ClassLoad*` `ClassUnload*` Rückrufe und in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="411bf-127">Steuert die `ExceptionCLRCatcher*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="411bf-128">Steuert die Rückrufe [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) und [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="411bf-129">Steuert die `FunctionEnter*` `FunctionLeave*` `FunctionTailCall*` [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md), und.</span><span class="sxs-lookup"><span data-stu-id="411bf-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="411bf-130">Steuert den [exceptiondent](icorprofilercallback-exceptionthrown-method.md) -Rückruf und `ExceptionSearch*` die `ExceptionOSHandler*` `ExceptionUnwind*` Rückrufe,, und `ExceptionCatcher*` in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="411bf-131">Steuert den [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) -Rückruf in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="411bf-132">Steuert die Rückrufe [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionfinished-method.md), [muvedreferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [objectsallogatedbyclass](icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [Lenker created](icorprofilercallback2-handlecreated-method.md), [Lenker](icorprofilercallback2-handledestroyed-method.md)und [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) in den `ICorProfilerCallback*` Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="411bf-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="411bf-133">Wenn `COR_PRF_MONITOR_GC` zugeordnet ist, wird das gleichzeitige Garbage Collection ausgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="411bf-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="411bf-134">Steuert die `JITCompilation*` Rückrufe, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)und [JITInlining](icorprofilercallback-jitinlining-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="411bf-135">Steuert die Rückrufe `ModuleLoad*` , `ModuleUnload*` und [moduleattachedonassembly](icorprofilercallback-moduleattachedtoassembly-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="411bf-136">Steuert den [ObjectAllocated](icorprofilercallback-objectallocated-method.md) -Rückruf in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="411bf-137">Steuert die `Remoting*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="411bf-138">Steuert, ob die `Remoting*`-Rückrufe asynchrone Ereignisse überwachen.</span><span class="sxs-lookup"><span data-stu-id="411bf-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="411bf-139">Steuert, ob ein Cookie an `Remoting*`-Rückrufe übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="411bf-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="411bf-140">Steuert die Rückrufe `RuntimeSuspend*` , `RuntimeResume*` , [runtimethleseangeh](icorprofilercallback-runtimethreadsuspended-method.md)alten und [runtimethrerunning](icorprofilercallback-runtimethreadresumed-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="411bf-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="411bf-141">Steuert die Rückrufe [ThreadCreated](icorprofilercallback-threadcreated-method.md), [threadzerstört](icorprofilercallback-threaddestroyed-method.md), [threadassigneddeosthread](icorprofilercallback-threadassignedtoosthread-method.md)und [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) in den [ICorProfilerCallback](icorprofilercallback-interface.md) -und [ICorProfilerCallback2](icorprofilercallback2-interface.md) -Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="411bf-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a><span data-ttu-id="411bf-142">Flags zur Aktivierung von Funktionen</span><span class="sxs-lookup"><span data-stu-id="411bf-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="411bf-143">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-143">Member</span></span>|<span data-ttu-id="411bf-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411bf-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="411bf-145">Ermöglicht das Abrufen eines exakten `ClassID` für eine generische Funktion durch Aufrufen der [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode mit einem Wert, der `COR_PRF_FRAME_INFO` vom [FunctionEnter2](functionenter2-function.md) -Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="411bf-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="411bf-146">Aktiviert die Argument Ablauf Verfolgung mit dem [FunctionEnter2](functionenter2-function.md) -Rückruf oder dem [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Rückruf und der [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="411bf-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="411bf-147">Ermöglicht die Ablauf Verfolgung von Rückgabe Werten mit dem [FunctionLeave2](functionleave2-function.md) -Rückruf oder dem [FunctionLeave3WithInfo](functionleave3withinfo-function.md) -Rückruf und der [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="411bf-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="411bf-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="411bf-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="411bf-149">Prozessinternes Debuggen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="411bf-149">In process debugging is not supported.</span></span> <span data-ttu-id="411bf-150">Dieses Flag hat keine Wirkung.</span><span class="sxs-lookup"><span data-stu-id="411bf-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="411bf-151">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="411bf-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="411bf-152">Ermöglicht dem Profiler das Abrufen von Il-to-Native-Zuordnungen mithilfe von [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span><span class="sxs-lookup"><span data-stu-id="411bf-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="411bf-153">In .NET Framework, Version 2.0 werden Zuordnungen zwischen IL-Code und systemeigenem Code von der CLR immer nachverfolgt, daher gilt dieses Flag immer als gesetzt.</span><span class="sxs-lookup"><span data-stu-id="411bf-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="411bf-154">Teilt der CLR mit, dass der Profiler u. U. über Objektzuordnungen benachrichtigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="411bf-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="411bf-155">Dies muss während der Initialisierung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="411bf-155">This flag must be set during initialization.</span></span> <span data-ttu-id="411bf-156">Dies ermöglicht es dem Profiler, das- `COR_PRF_MONITOR_OBJECT_ALLOCATED` Flag zu verwenden, um [objectallokalisierte](icorprofilercallback-objectallocated-method.md) Rückrufe zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="411bf-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="411bf-157">Aktiviert Aufrufe der Methoden [requestrejit](icorprofilerinfo4-requestrejit-method.md) und [requestrevert](icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="411bf-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="411bf-158">Der Profiler muss dieses Flag beim Start festlegen.</span><span class="sxs-lookup"><span data-stu-id="411bf-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="411bf-159">Wenn der Profiler dieses Flag angibt, muss er auch `COR_PRF_DISABLE_ALL_NGEN_IMAGES` angeben.</span><span class="sxs-lookup"><span data-stu-id="411bf-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="411bf-160">Aktiviert Aufrufe der [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="411bf-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a><span data-ttu-id="411bf-161">Konfigurationsflags</span><span class="sxs-lookup"><span data-stu-id="411bf-161">Configuration flags</span></span>  
  
|<span data-ttu-id="411bf-162">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-162">Member</span></span>|<span data-ttu-id="411bf-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411bf-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="411bf-164">Bewirkt, dass die systemeigene Abbildsuche nach Abbildern (einschließlich durch Profiler verbesserte) sucht.</span><span class="sxs-lookup"><span data-stu-id="411bf-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="411bf-165">Wenn dieses Flag und das `COR_PRF_USE_PROFILE_IMAGES`-Flag beide angegeben sind, wird `COR_PRF_DISABLE_ALL_NGEN_IMAGES` verwendet.</span><span class="sxs-lookup"><span data-stu-id="411bf-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="411bf-166">Deaktiviert das gesamte Inlining.</span><span class="sxs-lookup"><span data-stu-id="411bf-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="411bf-167">Deaktiviert alle Codeoptimierungen.</span><span class="sxs-lookup"><span data-stu-id="411bf-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="411bf-168">Deaktiviert Sicherheitstransparenzprüfungen, die normalerweise während Just-In-Time (JIT)-Kompilierungen und dem Laden von Klassen für vollständig vertrauenswürdige Assemblys durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="411bf-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="411bf-169">Dies kann die Ausführung einiger Instrumentierungsvorgänge erleichtern.</span><span class="sxs-lookup"><span data-stu-id="411bf-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="411bf-170">Bewirkt, dass die systemeigene Abbildsuche nach durch Profiler verbesserten Abbildern sucht.</span><span class="sxs-lookup"><span data-stu-id="411bf-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="411bf-171">Wenn für eine Assembly kein durch Profiler verbessertes Bild gefunden wird, greift die Common Language Runtime für die betreffende Assembly wieder auf JIT zurück.</span><span class="sxs-lookup"><span data-stu-id="411bf-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="411bf-172">Wenn dieses Flag und das `COR_PRF_DISABLE_ALL_NGEN_IMAGES`-Flag beide angegeben sind, wird `COR_PRF_DISABLE_ALL_NGEN_IMAGES` verwendet.</span><span class="sxs-lookup"><span data-stu-id="411bf-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a><span data-ttu-id="411bf-173">Kombinierte Flags</span><span class="sxs-lookup"><span data-stu-id="411bf-173">Composite flags</span></span>  
  
|<span data-ttu-id="411bf-174">Member</span><span class="sxs-lookup"><span data-stu-id="411bf-174">Member</span></span>|<span data-ttu-id="411bf-175">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="411bf-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="411bf-176">Stellt alle `COR_PRF_MONITOR`-Flagwerte dar.</span><span class="sxs-lookup"><span data-stu-id="411bf-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="411bf-177">Stellt alle `COR_PRF_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.</span><span class="sxs-lookup"><span data-stu-id="411bf-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="411bf-178">Der Syntaxabschnitt gibt die einzelnen Flags an, die in dieser Bitmask vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="411bf-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="411bf-179">Aktiviert alle Rückrufereignisse.</span><span class="sxs-lookup"><span data-stu-id="411bf-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="411bf-180">Stellt alle `COR_PRF_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="411bf-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="411bf-181">Wenn Sie versuchen, eines dieser Flags nach der Initialisierung zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.</span><span class="sxs-lookup"><span data-stu-id="411bf-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="411bf-182">Stellt alle `COR_PRF_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern.</span><span class="sxs-lookup"><span data-stu-id="411bf-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411bf-183">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="411bf-183">Remarks</span></span>  
 <span data-ttu-id="411bf-184">Ein `COR_PRF_MONITOR` -Wert wird mit den Methoden [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) und [ICorProfilerInfo:: lteventmask](icorprofilerinfo-seteventmask-method.md) verwendet, um die Ereignis Benachrichtigungen zu definieren, die die Common Language Runtime an den Profiler sendet.</span><span class="sxs-lookup"><span data-stu-id="411bf-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="411bf-185">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="411bf-185">Requirements</span></span>  
 <span data-ttu-id="411bf-186">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="411bf-186">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411bf-187">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="411bf-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="411bf-188">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="411bf-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="411bf-189">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411bf-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411bf-190">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="411bf-190">See also</span></span>

- [<span data-ttu-id="411bf-191">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="411bf-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="411bf-192">GetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="411bf-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="411bf-193">SetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="411bf-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
