---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae6183f33b784a0ff79d11310b952949cf13bf58
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556193"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Benachrichtigt den Profiler an, wenn der symbolstream ein in-Memory-Modul aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `moduleId`  
 Der Bezeichner des Moduls im Arbeitsspeicher, deren symbolstream aktualisiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf wird gesteuert, indem die [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.  
  
> [!NOTE]
>  Dieses Ereignis wird derzeit nicht für Symbole implizit erstellt oder geändert wird, über ausgelöst <xref:System.Reflection.Emit> APIs.  
  
 Auch wenn Symbole vorab in einem Aufruf einer Überladung der verwalteten bereitgestellt werden <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> Methoden, die umfasst eine `rawSymbolStore` Argument an die Symbole für die Assembly, die Laufzeit kann die symbolische Daten nicht tatsächlich mit dem Modul zuordnen erst nachdem der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf ist aufgetreten. Dieses Ereignis bietet eine höhere Chance Symbole für diese Module zu sammeln.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [CorProfilerCallback7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
