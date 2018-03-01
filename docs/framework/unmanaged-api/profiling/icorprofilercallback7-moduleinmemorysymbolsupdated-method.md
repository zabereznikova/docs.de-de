---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7::ModuleInMemorySymbolsUpdated-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Benachrichtigt den Profiler an, wenn der symbolstream ein in-Memory-Modul aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 Der Bezeichner des in-Memory-Moduls, deren symbolstream aktualisiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf wird gesteuert durch Festlegen der [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.  
  
> [!NOTE]
>  Dieses Ereignis ist derzeit nicht für Symbole implizit erstellt oder geändert wird, über ausgelöst <xref:System.Reflection.Emit> APIs.  
  
 Selbst wenn Symbole vorab in einem Aufruf an eine der Überladungen der verwalteten bereitgestellt werden <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> Methoden, die umfasst eine `rawSymbolStore` Argument an die Symbole für die Assembly, die Common Language Runtime kann die symbolischen Daten nicht tatsächlich mit dem Modul zuordnen erst nachdem die [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf aufgetreten. Dieses Ereignis ermöglicht eine höhere Symbole für solche Modulen zu sammeln.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [SetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [CorProfilerCallback7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
