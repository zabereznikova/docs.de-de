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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b616017745d7cc33d57b1626b6c27c59a0a60a32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091173"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences-Methode
Benachrichtigt den Profiler mit Informationen über Stammverweise nach der Garbagecollection.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cRootRefs`  
 [in] Die Anzahl der Verweise in die `rootRefIds` Array.  
  
 `rootRefIds`  
 [in] Ein Array von Objekt-IDs, die entweder ein statisches Objekt oder ein Objekt auf dem Stapel zu verweisen.  
  
## <a name="remarks"></a>Hinweise  
 Beide `RootReferences` und [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise mindestens eine der anderen jedoch nicht beides, da die Informationen in übergeben `RootReferences2` ist eine Obermenge der, die übergebene `RootReferences`.  
  
 Es ist möglich, dass die `rootRefIds` Array kann ein null-Objekt enthalten. Beispielsweise werden alle Objektverweise, die auf dem Stapel deklariert werden als Stammelemente behandelt, durch den Garbage Collector und immer gemeldet.  
  
 Die Objekt-IDs von zurückgegebenen `RootReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann. Aus diesem Grund müssen Profiler nicht versuchen, Objekte, die beim Überprüfen einer `RootReferences` aufrufen. Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und problemlos überprüft werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
