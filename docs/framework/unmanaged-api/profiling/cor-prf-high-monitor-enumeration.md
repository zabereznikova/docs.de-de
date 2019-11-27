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
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR-Enumeration

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
Bietet zusätzlich zu den in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gefundenen Flags, die der Profiler beim Laden an die [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode angeben kann.  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Es sind keine Flags festgelegt.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Steuert den [ICorProfilerCallback6:: getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf zum Hinzufügen von Assemblyverweisen während des CLR-Assemblyverweises zum Schließen.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Steuert den [ICorProfilerCallback7:: moduleinmemorysymbolsupdates](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) -Rückruf für Aktualisierungen des einem in-Memory-Modul zugeordneten Symbol Datenstroms.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Steuert den [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) -Rückruf für die Angabe, wann eine dynamische Methode in eine Garbage Collection und entladen wurde. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|Nur .net Core 3,0 und höhere Versionen: deaktiviert die mehr [stufige Kompilierung](../../../core/whats-new/dotnet-core-3-0.md) für Profiler.|
|`COR_PRF_HIGH_BASIC_GC`|Nur .net Core 3,0 und höhere Versionen: bietet im Vergleich zu [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)eine Lightweight-Profil Erstellungs Option. Steuert nur die Rückrufe [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [garbagecollectionabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)und [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) . Im Gegensatz zum `COR_PRF_MONITOR_GC`-Flag deaktiviert `COR_PRF_HIGH_BASIC_GC` gleichzeitige Garbage Collection nicht.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|Nur .net Core 3,0 und höhere Versionen: aktiviert die Rückrufe " [muvedreferences](icorprofilercallback-movedreferences-method.md) " und " [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) " nur für komprimierende GCS.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|Nur .net Core 3,0 und höhere Versionen: ähnlich wie [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), stellt jedoch nur Informationen zu Objekt Zuordnungen für den großen Objekt Heap (Loh) bereit.|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern. Dies entspricht dem `COR_PRF_REQUIRE_PROFILE_IMAGE`-Flag in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.|  
  
## <a name="remarks"></a>Hinweise

Die `COR_PRF_HIGH_MONITOR` Flags werden mit dem `pdwEventsHigh`-Parameter der [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) -Methode und der [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode verwendet.  
  
Beginnend mit der .NET Framework 4.6.1 hat sich der Wert des `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` von 0 in `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002) geändert. Beginnend mit der .NET Framework 4.7.2 hat sich der Wert von `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` in `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`geändert.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` ist eine Bitmaske, die alle Flags darstellt, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, diese Flags an anderer Stelle zu ändern, führt dies zu einem Fehler `HRESULT`.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
**Header:** CorProf.idl, CorProf.h  
  
**Bibliothek:** CorGuids.lib  
  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [COR_PRF_MONITOR-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
