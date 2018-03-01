---
title: ICorProfilerCallback2::GarbageCollectionStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b721b990312f9acda5c9e0208f998793735d2cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted-Methode
Benachrichtigt den Profiler, dass die Garbagecollection gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cGenerations`  
 [in] Die Gesamtanzahl der Einträge in der `generationCollected` Array.  
  
 `generationCollected`  
 [in] Ein Array von booleschen Werten `true` Wenn die Generierung, der Index des Arrays entspricht von der diese Garbagecollection gesammelt wurden, andernfalls wird `false`.  
  
 Das Array wird durch den Wert indiziert die [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) -Enumeration, die die Ursache der Garbagecollection ausgelöst wurde.  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe, die diese Garbagecollection betreffen treten zwischen den `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) Rückruf. Diese Rückrufe müssen nicht im selben Thread ausgeführt.  
  
 Gefahrlos für den Profiler zum Überprüfen von Objekten in ihren ursprünglichen Speicherorten während der `GarbageCollectionStarted` Rückruf. Der Garbage Collector beginnt Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`. Nachdem der Profiler von diesem Rückruf zurückgegeben wurde, sollten der Profiler alle Objekt-IDs ungültig werden, bis er erhält eine `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
