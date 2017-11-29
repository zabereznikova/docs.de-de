---
title: ICorProfilerCallback4::MovedReferences2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.MovedReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8137d944081475095509150cce84a611b7030eb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4movedreferences2-method"></a>ICorProfilerCallback4::MovedReferences2-Methode
Wird aufgerufen, um das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbage Collection zu melden. Diese Methode wird aufgerufen, wenn der Profiler implementiert hat die [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) Schnittstelle. Dieser Rückruf ersetzt die [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) -Methode, weil er größere Bereiche von Objekten melden kann, deren Länge überschreiten, was in einem ulong-Typ ausgedrückt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a>Parameter  
 `cMovedObjectIDRanges`  
 [in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der komprimierenden Garbage Collection verschoben wurden. Das heißt, der Wert von `cMovedObjectIDRanges` entspricht der Gesamtgröße der Arrays `oldObjectIDRangeStart`, `newObjectIDRangeStart` und `cObjectIDRangeLength`.  
  
 Die nächsten drei Argumente von `MovedReferences2` sind parallele Arrays. Mit anderen Worten, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` und `cObjectIDRangeLength[i]` betreffen alle einen einzelnen Block zusammenhängender Objekte.  
  
 `oldObjectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die alte (vor der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `newObjectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die neue (nach der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `cObjectIDRangeLength`  
 [in] Ein Array von Ganzzahlen, von denen jede die Größe eines Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.  
  
 Es wird eine Größe für jeden Block angegeben, auf den im `oldObjectIDRangeStart`-Array und im `newObjectIDRangeStart`-Array verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Ein komprimierender Garbage Collector gibt den von inaktiven Objekten belegten Arbeitsspeicher frei und komprimiert diesen freigegebenen Speicherplatz. Folglich könnten aktive Objekte innerhalb des Heaps verschoben werden, und `ObjectID`-Werte, die von vorherigen Benachrichtigungen verteilt wurden, könnten sich möglicherweise ändern.  
  
 Angenommen, ein vorhandener `ObjectID`-Wert (`oldObjectID`) liegt innerhalb des folgenden Bereichs:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 In diesem Fall ist der Offset vom Anfang des Bereichs bis zum Anfang des Objekts wie folgt:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Für jeden Wert von `i`, der im folgenden Bereich liegt:  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 können Sie die neue `ObjectID` wie folgt berechnen:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 Keiner der `ObjectID`-Werte, die von `MovedReferences2` übergeben wurden, ist während des Rückrufs selbst gültig, weil der Garbage Collector zu diesem Zeitpunkt möglicherweise noch Objekte von alten Speicherorten an neue Speicherorte verschiebt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `MovedReferences2`-Aufrufs zu überprüfen. Ein [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf gibt an, dass alle Objekte an die neuen Speicherorte verschoben wurden und die Überprüfung ausgeführt werden kann.  
  
 Wenn der Profiler implementiert die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) und [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) Schnittstellen, die `MovedReferences2` Methode wird aufgerufen, bevor die [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) -Methode, aber nur, wenn die `MovedReferences2` -Methode erfolgreich zurückgegeben. Profiler können ein HRESULT von der Methode `MovedReferences2` zurückgeben, um zu vermeiden, dass die zweite Methode aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [MovedReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)  
 [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
