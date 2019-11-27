---
title: COR_PRF_HIGH_MONITOR-Enumeration
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: fc0251624738a06d1be7081ebd099e97f7278a15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283143"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="83bc3-102">COR_PRF_HIGH_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="83bc3-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="83bc3-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="83bc3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="83bc3-104">Bietet zusätzlich zu den in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gefundenen Flags, die der Profiler beim Laden an die [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode angeben kann.</span><span class="sxs-lookup"><span data-stu-id="83bc3-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bc3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83bc3-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="83bc3-106">Member</span><span class="sxs-lookup"><span data-stu-id="83bc3-106">Members</span></span>  
  
|<span data-ttu-id="83bc3-107">Member</span><span class="sxs-lookup"><span data-stu-id="83bc3-107">Member</span></span>|<span data-ttu-id="83bc3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83bc3-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="83bc3-109">Es sind keine Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83bc3-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="83bc3-110">Steuert den [ICorProfilerCallback6:: getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf zum Hinzufügen von Assemblyverweisen während des CLR-Assemblyverweises zum Schließen.</span><span class="sxs-lookup"><span data-stu-id="83bc3-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="83bc3-111">Steuert den [ICorProfilerCallback7:: moduleinmemorysymbolsupdates](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) -Rückruf für Aktualisierungen des einem in-Memory-Modul zugeordneten Symbol Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="83bc3-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="83bc3-112">Steuert den [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) -Rückruf für die Angabe, wann eine dynamische Methode in eine Garbage Collection und entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="83bc3-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="83bc3-113">Nur .net Core 3,0 und höhere Versionen: deaktiviert die mehr [stufige Kompilierung](../../../core/whats-new/dotnet-core-3-0.md) für Profiler.</span><span class="sxs-lookup"><span data-stu-id="83bc3-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="83bc3-114">Nur .net Core 3,0 und höhere Versionen: bietet im Vergleich zu [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)eine Lightweight-Profil Erstellungs Option.</span><span class="sxs-lookup"><span data-stu-id="83bc3-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="83bc3-115">Steuert nur die Rückrufe [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [garbagecollectionabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)und [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="83bc3-115">Controls only the  [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="83bc3-116">Im Gegensatz zum `COR_PRF_MONITOR_GC`-Flag deaktiviert `COR_PRF_HIGH_BASIC_GC` gleichzeitige Garbage Collection nicht.</span><span class="sxs-lookup"><span data-stu-id="83bc3-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="83bc3-117">Nur .net Core 3,0 und höhere Versionen: aktiviert die Rückrufe " [muvedreferences](icorprofilercallback-movedreferences-method.md) " und " [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) " nur für komprimierende GCS.</span><span class="sxs-lookup"><span data-stu-id="83bc3-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="83bc3-118">Nur .net Core 3,0 und höhere Versionen: ähnlich wie [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), stellt jedoch nur Informationen zu Objekt Zuordnungen für den großen Objekt Heap (Loh) bereit.</span><span class="sxs-lookup"><span data-stu-id="83bc3-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="83bc3-119">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern.</span><span class="sxs-lookup"><span data-stu-id="83bc3-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="83bc3-120">Dies entspricht dem `COR_PRF_REQUIRE_PROFILE_IMAGE`-Flag in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="83bc3-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="83bc3-121">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.</span><span class="sxs-lookup"><span data-stu-id="83bc3-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="83bc3-122">Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="83bc3-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="83bc3-123">Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.</span><span class="sxs-lookup"><span data-stu-id="83bc3-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83bc3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83bc3-124">Remarks</span></span>

<span data-ttu-id="83bc3-125">Die `COR_PRF_HIGH_MONITOR` Flags werden mit dem `pdwEventsHigh`-Parameter der [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) -Methode und der [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="83bc3-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="83bc3-126">Beginnend mit der .NET Framework 4.6.1 hat sich der Wert des `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` von 0 in `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002) geändert.</span><span class="sxs-lookup"><span data-stu-id="83bc3-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="83bc3-127">Beginnend mit der .NET Framework 4.7.2 hat sich der Wert von `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` in `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`geändert.</span><span class="sxs-lookup"><span data-stu-id="83bc3-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="83bc3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` ist eine Bitmaske, die alle Flags darstellt, die nur während der Initialisierung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="83bc3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="83bc3-129">Wenn Sie versuchen, diese Flags an anderer Stelle zu ändern, führt dies zu einem Fehler `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="83bc3-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="83bc3-130">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="83bc3-130">Requirements</span></span>

<span data-ttu-id="83bc3-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83bc3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="83bc3-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83bc3-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="83bc3-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83bc3-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="83bc3-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83bc3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bc3-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83bc3-135">See also</span></span>

- [<span data-ttu-id="83bc3-136">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="83bc3-136">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="83bc3-137">COR_PRF_MONITOR-Enumeration</span><span class="sxs-lookup"><span data-stu-id="83bc3-137">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="83bc3-138">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83bc3-138">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
