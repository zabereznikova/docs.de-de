---
title: ICorProfilerCallback2::SurvivingReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
ms.openlocfilehash: a83f8566dfe8e1b612f67d95a0e69947b72704ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439595"
---
# <a name="icorprofilercallback2survivingreferences-method"></a>ICorProfilerCallback2::SurvivingReferences-Methode
Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cSurvivingObjectIDRanges`  
 [in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der nicht komprimierenden Garbage Collection beibehalten wurden. Dies bedeutet, dass der Wert von `cSurvivingObjectIDRanges` die Größe der Arrays `objectIDRangeStart` und `cObjectIDRangeLength`, die eine `ObjectID` bzw. eine Länge speichern, für jeden Objektblock darstellt.  
  
 Die nächsten zwei Argumente von `SurvivingReferences` sind parallele Arrays. `objectIDRangeStart` und `cObjectIDRangeLength` betreffen also alle den gleichen Block zusammenhängender Objekte.  
  
 `objectIDRangeStart`  
 [in] Ein Array von `ObjectID`-Werten, von denen jeder die Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.  
  
 `cObjectIDRangeLength`  
 [in] Ein Array von Ganzzahlen, von denen jede die Größe eines beibehaltenen Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.  
  
 Es wird eine Größe für jeden Block angegeben, auf den im `objectIDRangeStart`-Array verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Mit dieser Methode werden auf 64-Bit-Plattformen Größen für Objekte, die größer als 4 GB sind, als `MAX_ULONG` gemeldet. For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) method instead.  
  
 Die Elemente der `objectIDRangeStart`- und `cObjectIDRangeLength`-Arrays sollten wie folgt interpretiert werden, um festzustellen, ob ein Objekt bei der Garbage Collection beibehalten wurde. Angenommen, ein `ObjectID`-Wert (`ObjectID`) liegt innerhalb des folgenden Bereichs:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 Für jeden Wert von `i` im folgenden Bereich wurde das Objekt bei der Garbage Collection beibehalten:  
  
 0 <= `i` < `cSurvivingObjectIDRanges`  
  
 Eine nicht komprimierende Garbage Collection gibt den von "inaktiven" Objekten belegten Arbeitsspeicher frei, komprimiert diesen freigegebenen Speicherplatz jedoch nicht. Als Ergebnis wird Arbeitsspeicher an den Heap zurückgegeben, es werden jedoch keine "aktiven" Objekte verschoben.  
  
 Die CLR (Common Language Runtime) ruft `SurvivingReferences` für nicht komprimierende Garbage Collections auf. For compacting garbage collections, [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) is called instead. Eine einzelne Garbage Collection kann für eine Generation komprimierend und für eine andere nicht komprimierend sein. Für eine Garbage Collection einer bestimmten Generation empfängt der Profiler einen `SurvivingReferences`-Rückruf oder einen `MovedReferences`-Rückruf, nicht jedoch beides.  
  
 Es werden ggf. mehrere `SurvivingReferences`-Rückrufe während einer bestimmten Garbage Collection aufgrund der eingeschränkten internen Pufferung, mehrerer Threads, die bei der Garbage Collection des Servers gemeldet werden, oder anderer Gründe empfangen. Wenn mehrere Rückrufe während einer Garbage Collection erfolgen, sind die Informationen kumulativ. Alle Verweise, die in einen `SurvivingReferences`-Rückruf gemeldet werden, werden bei der Garbage Collection beibehalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [SurvivingReferences2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)
