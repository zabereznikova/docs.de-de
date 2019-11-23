---
title: ICorProfilerCallback4::MovedReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 37d5f5e8294bb87a8796d6dcae046864904b096b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439374"
---
# <a name="icorprofilercallback4movedreferences2-method"></a>ICorProfilerCallback4::MovedReferences2-Methode
Wird aufgerufen, um das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbage Collection zu melden. This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface. This callback replaces the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parameter  
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
  
 Keiner der `ObjectID`-Werte, die von `MovedReferences2` übergeben wurden, ist während des Rückrufs selbst gültig, weil der Garbage Collector zu diesem Zeitpunkt möglicherweise noch Objekte von alten Speicherorten an neue Speicherorte verschiebt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `MovedReferences2`-Aufrufs zu überprüfen. A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.  
  
 If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully. Profiler können ein HRESULT von der Methode `MovedReferences2` zurückgeben, um zu vermeiden, dass die zweite Methode aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [MovedReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
