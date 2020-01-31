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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865778"
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
  
## <a name="parameters"></a>Parameters  
 `cGenerations`  
 in Die Gesamtanzahl der Einträge im `generationCollected` Array.  
  
 `generationCollected`  
 in Ein Array von booleschen Werten, die `true` werden, wenn die Generierung, die dem Array Index entspricht, von dieser Garbage Collection erfasst wird. Andernfalls `false`.  
  
 Das Array wird durch einen Wert der [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) -Enumeration indiziert, die die Generierung angibt.  
  
 `reason`  
 in Ein Wert der [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) Enumeration, die den Grund angibt, warum die Garbage Collection induziert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Alle Rückrufe, die diese Garbage Collection betreffen, treten zwischen dem `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: garbagecollectionbeendete](icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf auf. Diese Rückrufe müssen nicht im selben Thread erfolgen.  
  
 Es ist sicher, dass der Profiler die Objekte an den ursprünglichen Speicherorten während des `GarbageCollectionStarted` Rückrufs überprüfen kann. Der Garbage Collector beginnt mit dem Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`. Nachdem der Profiler von diesem Rückruf zurückgegeben hat, sollte der Profiler alle Objekt-IDs als ungültig einsehen, bis er einen `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf empfängt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
