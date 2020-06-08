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
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499908"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences-Methode
Benachrichtigt den Profiler über Informationen über Stamm Verweise nach Garbage Collection.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cRootRefs`  
 in Die Anzahl der Verweise im `rootRefIds` Array.  
  
 `rootRefIds`  
 in Ein Array von Objekt-IDs, das entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist.  
  
## <a name="remarks"></a>Bemerkungen  
 Sowohl `RootReferences` als auch [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise einen oder den anderen, aber nicht beides, da die übergebenen Informationen `RootReferences2` eine supermenge von sind, die an übergebenen ist `RootReferences` .  
  
 Es ist möglich, dass das `rootRefIds` Array ein NULL-Objekt enthält. Beispielsweise werden alle Objekt Verweise, die auf dem Stapel deklariert sind, vom Garbage Collector als Stämme behandelt und werden immer gemeldet.  
  
 Die Objekt-IDs, die von zurückgegeben werden `RootReferences` , sind während des Rückrufs selbst nicht gültig, da die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten von alten Adressen zu neuen Adressen liegt. Daher dürfen Profiler nicht versuchen, Objekte während eines `RootReferences` Aufrufens zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
