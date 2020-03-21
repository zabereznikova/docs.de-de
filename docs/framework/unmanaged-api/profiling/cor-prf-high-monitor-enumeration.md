---
title: COR_PRF_HIGH_MONITOR-Enumeration
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175212"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="881f3-102">COR_PRF_HIGH_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="881f3-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="881f3-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="881f3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="881f3-104">Stellt zusätzlich zu den in [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) der COR_PRF_MONITOR-Enumeration gefundenen Flags bereit, die der Profiler beim Laden für die [ICorProfilerInfo5::SetEventMask2-Methode](icorprofilerinfo5-seteventmask2-method.md) angeben kann.</span><span class="sxs-lookup"><span data-stu-id="881f3-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="881f3-105">Syntax</span></span>  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED |
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="881f3-106">Members</span><span class="sxs-lookup"><span data-stu-id="881f3-106">Members</span></span>  
  
|<span data-ttu-id="881f3-107">Member</span><span class="sxs-lookup"><span data-stu-id="881f3-107">Member</span></span>|<span data-ttu-id="881f3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="881f3-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="881f3-109">Es sind keine Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="881f3-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="881f3-110">Steuert den [ICorProfilerCallback6::GetAssemblyReference-Rückruf](icorprofilercallback6-getassemblyreferences-method.md) zum Hinzufügen von Assemblyverweisen während des CLR-Assemblyverweisabschlusslaufs.</span><span class="sxs-lookup"><span data-stu-id="881f3-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="881f3-111">Steuert den [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) Rückruf für Aktualisierungen des Symbolstreams, der einem In-Memory-Modul zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="881f3-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="881f3-112">Steuert den [ICorProfilerCallback9::DynamicMethodUnloaded-Rückruf,](icorprofilercallback9-dynamicmethodunloaded-method.md) um anzugeben, wann eine dynamische Methode Garbage Collection und Deloaded wurde.</span><span class="sxs-lookup"><span data-stu-id="881f3-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="881f3-113">.NET Core 3.0 und neuere Versionen: Deaktiviert [die gestufte Kompilierung](../../../core/whats-new/dotnet-core-3-0.md) für Profiler.</span><span class="sxs-lookup"><span data-stu-id="881f3-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="881f3-114">.NET Core 3.0 und neuere Versionen: Bietet eine [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)einfache GC-Profilerstellungsoption im Vergleich zu .</span><span class="sxs-lookup"><span data-stu-id="881f3-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="881f3-115">Steuert nur die [Rückrufe GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)und [GetGenerationBounds.](icorprofilerinfo2-getgenerationbounds-method.md)</span><span class="sxs-lookup"><span data-stu-id="881f3-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="881f3-116">Deaktiviert `COR_PRF_MONITOR_GC` im `COR_PRF_HIGH_BASIC_GC` Gegensatz zum Flag die gleichzeitige Garbage Collection nicht.</span><span class="sxs-lookup"><span data-stu-id="881f3-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="881f3-117">.NET Core 3.0 und neuere Versionen: Aktiviert die [Rückrufe MovedReferences](icorprofilercallback-movedreferences-method.md) und [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) nur zum Komprimieren von GCs.</span><span class="sxs-lookup"><span data-stu-id="881f3-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="881f3-118">.NET Core 3.0 und neuere [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)Versionen nur: Ähnlich wie , stellt jedoch Nur Informationen zu Objektzuordnungen für den großen Objektheap (LOH) bereit.</span><span class="sxs-lookup"><span data-stu-id="881f3-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="881f3-119">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern.</span><span class="sxs-lookup"><span data-stu-id="881f3-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="881f3-120">Sie entspricht `COR_PRF_REQUIRE_PROFILE_IMAGE` der Flagge in der COR_PRF_MONITOR-Aufzählung. [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="881f3-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="881f3-121">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.</span><span class="sxs-lookup"><span data-stu-id="881f3-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="881f3-122">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="881f3-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="881f3-123">Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.</span><span class="sxs-lookup"><span data-stu-id="881f3-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="881f3-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="881f3-124">Remarks</span></span>

<span data-ttu-id="881f3-125">Die `COR_PRF_HIGH_MONITOR` Flags werden `pdwEventsHigh` mit dem Parameter der Methoden [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) und [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="881f3-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="881f3-126">Beginnend mit .NET Framework 4.6.1 wird `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` der Wert `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` der von 0 auf (0x00000002) geändert.</span><span class="sxs-lookup"><span data-stu-id="881f3-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="881f3-127">Ab .NET Framework 4.7.2 änderte sich `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`der Wert von .</span><span class="sxs-lookup"><span data-stu-id="881f3-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="881f3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE`ist als Bitmaske gedacht, die alle Flags darstellt, die nur während der Initialisierung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="881f3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="881f3-129">Der Versuch, eines dieser Flags an `HRESULT`anderer Stelle zu ändern, führt zu einem fehlgeschlagenen .</span><span class="sxs-lookup"><span data-stu-id="881f3-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="881f3-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="881f3-130">Requirements</span></span>

<span data-ttu-id="881f3-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="881f3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="881f3-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="881f3-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="881f3-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="881f3-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="881f3-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="881f3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881f3-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="881f3-135">See also</span></span>

- [<span data-ttu-id="881f3-136">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="881f3-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="881f3-137">COR_PRF_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="881f3-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="881f3-138">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="881f3-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
