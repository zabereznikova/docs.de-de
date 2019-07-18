---
title: ICorProfilerCallback2::GarbageCollectionStarted-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4f639f9794002748e1019821514c546e4f4429f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746865"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted-Methode
Benachrichtigt den Profiler an, dass der Garbagecollection gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parameter  
 `cGenerations`  
 [in] Die Gesamtanzahl von Einträgen in der `generationCollected` Array.  
  
 `generationCollected`  
 [in] Ein Array von booleschen Werten, die `true` Wenn die Generation, die Index des Arrays entspricht, von diese Garbagecollection gesammelt werden, andernfalls wird `false`.  
  
 Das Array wird indiziert, durch den Wert der [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt.  
  
 `reason`  
 [in] Der Wert der [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) -Enumeration, der gibt an, die Ursache der Garbagecollection ausgelöst wurde.  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe, die diese Garbagecollection betreffen, treten zwischen den `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) Rückruf. Diese Rückrufe müssen nicht auf dem gleichen Thread erfolgen.  
  
 Es ist sicher für den Profiler zum Überprüfen von Objekten in ihren ursprünglichen Speicherorten während der die `GarbageCollectionStarted` Rückruf. Der Garbage collection beginnt das Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`. Nachdem der Profiler von diesem Rückruf zurückgegeben wurde, sollten der Profiler alle Objekt-IDs ungültig werden, bis er erhält eine `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
