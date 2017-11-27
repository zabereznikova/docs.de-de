---
title: COR_PRF_HIGH_MONITOR-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1df931796b32b6bea49e8b69da02d39e6a4803e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corprfhighmonitor-enumeration"></a>COR_PRF_HIGH_MONITOR-Enumeration
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt Kennzeichen neben solche, die der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration, die der Profiler angeben kann, zu der [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode, wenn es geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES     = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED     = 0x00000002,     
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE       = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH      = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE           = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Es sind keine Flags festgelegt.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Steuert die [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf für das Hinzufügen von Assemblyverweisen während der CLR Assemblyverweis-abschlussdurchlauf.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Steuert die [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) Rückruf nach Updates für die symbolstream ein in-Memory-Modul.|  
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern. Entspricht der `COR_PRF_REQUIRE_PROFILE_IMAGE` -flag in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Stellt alle `COR_PRF_HIGH_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, eines dieser Flags an einem anderen Ort zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_PRF_HIGH_MONITOR` Flags werden verwendet, mit der `pdwEventsHigh` Parameter von der [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) und [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methoden.  
  
 Beginnend mit der [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], den Wert von der `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` geändert von 0 bis `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0 x 00000002).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [COR_PRF_MONITOR-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [ICorProfilerInfo5-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
