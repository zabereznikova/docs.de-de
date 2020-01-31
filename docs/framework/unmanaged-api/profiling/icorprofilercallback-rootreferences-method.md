---
title: ICorProfilerCallback::RootReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 948628f469eecabfbbe792dcc3edf2e1204ffc36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865960"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences-Methode
Benachrichtigt den Profiler über Informationen über Stamm Verweise nach Garbage Collection.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parameters  
 `cRootRefs`  
 in Die Anzahl der Verweise im `rootRefIds` Array.  
  
 `rootRefIds`  
 in Ein Array von Objekt-IDs, das entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist.  
  
## <a name="remarks"></a>Hinweise  
 Sowohl `RootReferences` als auch [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise einen oder den anderen, aber nicht beides, da die in `RootReferences2` übergebenen Informationen eine supermenge von sind, die `RootReferences`übergebenen ist.  
  
 Es ist möglich, dass das `rootRefIds` Array ein NULL-Objekt enthält. Beispielsweise werden alle Objekt Verweise, die auf dem Stapel deklariert sind, vom Garbage Collector als Stämme behandelt und werden immer gemeldet.  
  
 Die Objekt-IDs, die von `RootReferences` zurückgegeben werden, sind während des Rückrufs nicht gültig, da die Garbage Collection möglicherweise in der Mitte des Verschiebens von Objekten von alten Adressen zu neuen Adressen liegt. Daher dürfen Profiler nicht versuchen, Objekte während eines `RootReferences` Aufrufens zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
