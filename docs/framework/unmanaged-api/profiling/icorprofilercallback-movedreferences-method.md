---
title: ICorProfilerCallback::MovedReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca0d1c647ed23d9540377068b7fd75fbb88bdfeb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480753"
---
# <a name="icorprofilercallbackmovedreferences-method"></a>ICorProfilerCallback::MovedReferences-Methode
Wird aufgerufen, um das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbage Collection zu melden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cMovedObjectIDRanges`  
 [in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der komprimierenden Garbage Collection verschoben wurden. Das heißt, der Wert von `cMovedObjectIDRanges` entspricht der Gesamtgröße der Arrays `oldObjectIDRangeStart`, `newObjectIDRangeStart` und `cObjectIDRangeLength`.  
  
 Die nächsten drei Argumente von `MovedReferences` sind parallele Arrays. Mit anderen Worten, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` und `cObjectIDRangeLength[i]` betreffen alle einen einzelnen Block zusammenhängender Objekte.  
  
 `oldObjectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die alte (vor der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `newObjectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die neue (nach der Garbage Collection vorhandene) Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `cObjectIDRangeLength`  
 [in] Ein Array von Ganzzahlen, von denen jede die Größe eines Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.  
  
 Es wird eine Größe für jeden Block angegeben, auf den im `oldObjectIDRangeStart`-Array und im `newObjectIDRangeStart`-Array verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Mit dieser Methode werden auf 64-Bit-Plattformen Größen für Objekte, die größer als 4 GB sind, als `MAX_ULONG` gemeldet. Rufen Sie die Größe der Objekte, die größer als 4 GB sind mit den [icorprofilercallback4:: Movedreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) Methode stattdessen.  
  
 Ein komprimierender Garbage Collector gibt den von inaktiven Objekten belegten Arbeitsspeicher frei und komprimiert diesen freigegebenen Speicherplatz. Folglich könnten aktive Objekte innerhalb des Heaps verschoben werden, und `ObjectID`-Werte, die von vorherigen Benachrichtigungen verteilt wurden, könnten sich möglicherweise ändern.  
  
 Angenommen, ein vorhandener `ObjectID`-Wert (`oldObjectID`) liegt innerhalb des folgenden Bereichs:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 In diesem Fall ist der Offset vom Anfang des Bereichs bis zum Anfang des Objekts wie folgt:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Für jeden Wert von `i`, der im folgenden Bereich liegt:  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 können Sie die neue `ObjectID` wie folgt berechnen:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 Keiner der `ObjectID`-Werte, die von `MovedReferences` übergeben wurden, ist während des Rückrufs selbst gültig, weil die Garbage Collection zu diesem Zeitpunkt möglicherweise noch Objekte von alten Speicherorten an neue Speicherorte verschiebt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `MovedReferences`-Aufrufs zu überprüfen. Ein [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) -Rückruf gibt an, dass alle Objekte an die neuen Speicherorte verschoben wurden und die Überprüfung ausgeführt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [MovedReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
