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
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR-Enumeration

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
Stellt zusätzlich zu den in [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) der COR_PRF_MONITOR-Enumeration gefundenen Flags bereit, die der Profiler beim Laden für die [ICorProfilerInfo5::SetEventMask2-Methode](icorprofilerinfo5-seteventmask2-method.md) angeben kann.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Es sind keine Flags festgelegt.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Steuert den [ICorProfilerCallback6::GetAssemblyReference-Rückruf](icorprofilercallback6-getassemblyreferences-method.md) zum Hinzufügen von Assemblyverweisen während des CLR-Assemblyverweisabschlusslaufs.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Steuert den [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) Rückruf für Aktualisierungen des Symbolstreams, der einem In-Memory-Modul zugeordnet ist.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Steuert den [ICorProfilerCallback9::DynamicMethodUnloaded-Rückruf,](icorprofilercallback9-dynamicmethodunloaded-method.md) um anzugeben, wann eine dynamische Methode Garbage Collection und Deloaded wurde. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET Core 3.0 und neuere Versionen: Deaktiviert [die gestufte Kompilierung](../../../core/whats-new/dotnet-core-3-0.md) für Profiler.|
|`COR_PRF_HIGH_BASIC_GC`|.NET Core 3.0 und neuere Versionen: Bietet eine [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)einfache GC-Profilerstellungsoption im Vergleich zu . Steuert nur die [Rückrufe GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)und [GetGenerationBounds.](icorprofilerinfo2-getgenerationbounds-method.md) Deaktiviert `COR_PRF_MONITOR_GC` im `COR_PRF_HIGH_BASIC_GC` Gegensatz zum Flag die gleichzeitige Garbage Collection nicht.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET Core 3.0 und neuere Versionen: Aktiviert die [Rückrufe MovedReferences](icorprofilercallback-movedreferences-method.md) und [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) nur zum Komprimieren von GCs.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3.0 und neuere [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)Versionen nur: Ähnlich wie , stellt jedoch Nur Informationen zu Objektzuordnungen für den großen Objektheap (LOH) bereit.|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern. Sie entspricht `COR_PRF_REQUIRE_PROFILE_IMAGE` der Flagge in der COR_PRF_MONITOR-Aufzählung. [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.|  
  
## <a name="remarks"></a>Bemerkungen

Die `COR_PRF_HIGH_MONITOR` Flags werden `pdwEventsHigh` mit dem Parameter der Methoden [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) und [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) verwendet.  
  
Beginnend mit .NET Framework 4.6.1 wird `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` der Wert `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` der von 0 auf (0x00000002) geändert. Ab .NET Framework 4.7.2 änderte sich `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`der Wert von .

`COR_PRF_HIGH_MONITOR_IMMUTABLE`ist als Bitmaske gedacht, die alle Flags darstellt, die nur während der Initialisierung festgelegt werden können. Der Versuch, eines dieser Flags an `HRESULT`anderer Stelle zu ändern, führt zu einem fehlgeschlagenen .

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
**Header:** CorProf.idl, CorProf.h  
  
**Bibliothek:** CorGuids.lib  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsenumerationen](profiling-enumerations.md)
- [COR_PRF_MONITOR-Enumeration](cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5-Schnittstelle](icorprofilerinfo5-interface.md)
