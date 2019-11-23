---
title: ICorProfilerCallback4::SurvivingReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: 3178d099db96d52f0238cfcf7e055e761687ce30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430097"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a>ICorProfilerCallback4::SurvivingReferences2-Methode
Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection. This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface. This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cSurvivingObjectIDRanges`  
 [in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der nicht komprimierenden Garbage Collection beibehalten wurden. Dies bedeutet, dass der Wert von `cSurvivingObjectIDRanges` die Größe der Arrays `objectIDRangeStart` und `cObjectIDRangeLength`, die eine `ObjectID` bzw. eine Länge speichern, für jeden Objektblock darstellt.  
  
 Die nächsten zwei Argumente von `SurvivingReferences2` sind parallele Arrays. `objectIDRangeStart` und `cObjectIDRangeLength` betreffen also alle den gleichen Block zusammenhängender Objekte.  
  
 `objectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `cObjectIDRangeLength`  
 [in] Ein Array von Ganzzahlen, von denen jede die Größe eines beibehaltenen Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.  
  
 Es wird eine Größe für jeden Block angegeben, auf den im `objectIDRangeStart`-Array verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente der `objectIDRangeStart`- und `cObjectIDRangeLength`-Arrays sollten wie folgt interpretiert werden, um festzustellen, ob ein Objekt bei der Garbage Collection beibehalten wurde. Angenommen, ein `ObjectID`-Wert (`ObjectID`) liegt innerhalb des folgenden Bereichs:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 Für jeden Wert von `i` im folgenden Bereich wurde das Objekt bei der Garbage Collection beibehalten:  
  
 0 <= `i` < `cSurvivingObjectIDRanges`  
  
 Eine nicht komprimierende Garbage Collection gibt den von "inaktiven" Objekten belegten Arbeitsspeicher frei, komprimiert diesen freigegebenen Speicherplatz jedoch nicht. Als Ergebnis wird Arbeitsspeicher an den Heap zurückgegeben, es werden jedoch keine "aktiven" Objekte verschoben.  
  
 Die CLR (Common Language Runtime) ruft `SurvivingReferences2` für nicht komprimierende Garbage Collections auf. For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead. Eine einzelne Garbage Collection kann für eine Generation komprimierend und für eine andere nicht komprimierend sein. For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.  
  
 Es werden ggf. mehrere `SurvivingReferences2`-Rückrufe während einer bestimmten Garbage Collection aufgrund der eingeschränkten internen Pufferung, mehrerer Rückrufe während der Garbage Collection des Servers oder anderer Gründe empfangen. Wenn mehrere Rückrufe während einer Garbage Collection erfolgen, sind die Informationen kumulativ. Alle Verweise, die in einen `SurvivingReferences2`-Rückruf gemeldet werden, werden bei der Garbage Collection beibehalten.  
  
 If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully. Profiler können ein HRESULT von der Methode `SurvivingReferences2` zurückgeben, um zu vermeiden, dass die zweite Methode aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
