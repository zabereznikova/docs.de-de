---
title: ICorProfilerCallback::RootReferences-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd057538450deeb46a72178c725103e04a8dd126
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences-Methode
Benachrichtigt den Profiler mit Informationen zu Stammverweisen nach der Garbagecollection.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a>Parameter  
 `cRootRefs`  
 [in] Die Anzahl der Verweise in der `rootRefIds` Array.  
  
 `rootRefIds`  
 [in] Ein Array von Objekt-IDs, die kein statisches Objekt oder ein Objekt auf dem Stapel zu verweisen.  
  
## <a name="remarks"></a>Hinweise  
 Beide `RootReferences` und [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise eine oder andere, jedoch nicht beides, da die Informationen im übergeben `RootReferences2` ist eine Obermenge der übergebenen `RootReferences`.  
  
 Es ist möglich, dass die `rootRefIds` Array kann ein null-Objekt enthalten. Beispielsweise alle Objektverweise, die auf dem Stapel deklariert werden als Stammelemente behandelt, durch den Garbage Collector und werden immer gemeldet werden.  
  
 Die Objekt-IDs zurückgegebenes `RootReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann. Aus diesem Grund müssen Profiler nicht versuchen, Objekte beim Untersuchen einer `RootReferences` aufrufen. Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und können problemlos geprüft werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
