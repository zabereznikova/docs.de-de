---
title: COR_PRF_HIGH_MONITOR-Enumeration
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b29fc50e4bda23053c239292956f9b2cd0c628a3
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268077"
---
# <a name="corprfhighmonitor-enumeration"></a>COR_PRF_HIGH_MONITOR-Enumeration
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt Kennzeichen neben denen in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration, die der Profiler, um angeben kann die [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode, wenn es geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
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
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Steuerelemente der [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf für das Hinzufügen von Assemblyverweisen während der CLR Assemblyverweis-abschlussdurchlauf.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Steuerelemente der [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) Rückruf für Aktualisierungen der symbolstream ein in-Memory-Modul.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Steuerelemente der [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) Rückruf für den, der angibt, wenn eine dynamische Methode Garbage Collector wurde gesammelt und entladen. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET Core 3.0 und höheren Versionen: Deaktiviert die [Ebenen Kompilierung](../../../core/whats-new/dotnet-core-3-0.md) für Tools für die profilerstellung.|
|`COR_PRF_HIGH_BASIC_GC`|.NET Core 3.0 und höheren Versionen: Bietet eine vereinfachte GC-Option die profilerstellung im Vergleich zu [ `COR_PRF_MONITOR_GC` ](cor-prf-monitor-enumeration.md). Steuert nur die [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), und [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) Rückrufe. Im Gegensatz zu den `COR_PRF_MONITOR_GC` Flag `COR_PRF_HIGH_BASIC_GC` nicht gleichzeitige Garbagecollection deaktiviert.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET Core 3.0 und höheren Versionen: Ermöglicht die [MovedReferences](icorprofilercallback-movedreferences-method.md) und [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) Rückrufe für komprimierende globale Kataloge.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3.0 und höheren Versionen: Ähnlich wie [ `COR_PRF_MONITOR_OBJECT_ALLOCATED` ](cor-prf-monitor-enumeration.md), sondern enthält Informationen zum objektzuordnungen für den Large Object Heap (LOH) nur.|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern. Dies entspricht der `COR_PRF_REQUIRE_PROFILE_IMAGE` -flag in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_PRF_HIGH_MONITOR` Flags werden verwendet, mit der `pdwEventsHigh` Parameter, der die [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) und [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methoden.  
  
Ab .NET Framework 4.6.1, den Wert des der `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` geändert von 0 bis `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0 x 00000002). Ab .NET Framework 4.7.2, deren Wert geändert von `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` zu `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` dient eine Bitmaske, die alle Flags darstellt, die nur während der Initialisierung festgelegt werden kann. So ändern Sie eines dieser Flags an anderer Stelle zu einem fehlgeschlagenen führt Versuch `HRESULT`.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [COR_PRF_MONITOR-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
