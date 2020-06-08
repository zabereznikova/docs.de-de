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
ms.openlocfilehash: f025f4c0bc0ec8e11decddcdf64be50f68955266
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499804"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted-Methode
Benachrichtigt den Codeprofiler, dass Garbage Collection gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parameter  
 `cGenerations`  
 in Die Gesamtanzahl der Einträge im `generationCollected` Array.  
  
 `generationCollected`  
 in Ein Array von booleschen Werten, die sind, `true` Wenn die Generierung, die dem Array Index entspricht, von diesem Garbage Collection erfasst wird, andernfalls `false` .  
  
 Das Array wird durch einen Wert der [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) -Enumeration indiziert, die die Generierung angibt.  
  
 `reason`  
 in Ein Wert der [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) Enumeration, die den Grund angibt, warum die Garbage Collection induziert wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Alle Rückrufe, die diese Garbage Collection betreffen, treten zwischen dem `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: garbagecollectionbeendete](icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf auf. Diese Rückrufe müssen nicht im selben Thread erfolgen.  
  
 Es ist sicher, dass der Profiler die Objekte an den ursprünglichen Speicherorten während des Rückrufs überprüfen kann `GarbageCollectionStarted` . Der Garbage Collector beginnt mit dem Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted` . Nachdem der Profiler von diesem Rückruf zurückgegeben hat, sollte der Profiler berücksichtigen, dass alle Objekt-IDs ungültig sind, bis er einen `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf empfängt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
