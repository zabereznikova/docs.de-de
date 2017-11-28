---
title: ICorProfilerCallback2::RootReferences2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.RootReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a0b2e23ba586e7a20ed11de6433b2d87cbe7219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2-Methode
Benachrichtigt den Profiler zu Stammverweisen, nach eine Garbagecollection aufgetreten ist. Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cRootRefs`  
 [in] Die Anzahl der Elemente in der `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays.  
  
 `rootRefIds`  
 [in] Ein Array von Objekt-IDs, von denen jeder ein statisches Objekt oder ein Objekt auf dem Stapel verweist. Elemente in der `rootKinds` Array enthalten Informationen zum Klassifizieren der entsprechenden Elemente in der `rootRefIds` Array.  
  
 `rootKinds`  
 [in] Ein Array von [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) Werte, die den Typ der Garbage Collection-Stamm angeben.  
  
 `rootFlags`  
 [in] Ein Array von [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) Werte, die die Eigenschaften eines Garbage Collection-Stamm zu beschreiben.  
  
 `rootIds`  
 [in] Ein Array von UINT_PTR Werten, die in eine ganze Zahl, die zusätzliche Informationen über die Garbage Collection-Stamm, abhängig vom Wert enthält den `rootKinds` Parameter.  
  
 Wenn der Typ des Stamms einen Stapel ist, ist die Stamm-ID für die Funktion, die die Variable enthält. Wenn die Stamm-ID 0 ist, ist die Funktion eine unbenannte Funktion, die für die CLR intern ist. Wenn der Typ des Stamms ein Handle ist, ist die Stamm-ID für die Garbage Collection-Handle. Die ID für die anderen Stammreferenztypen ist ein nicht transparenter Wert und sollte ignoriert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays sind parallele Arrays. D. h. `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, und `rootIds[i]` betreffen alle mit demselben Stamm.  
  
 Beide `RootReferences` und `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise eine Methode oder die andere aber nicht beides, da die Informationen im übergeben `RootReferences2` ist eine Obermenge der übergebenen `RootReferences`.  
  
 Es ist möglich, dass Einträge in `rootRefIds` als 0 (null), das bedeutet, dass der entsprechende Stammverweis null ist, und nicht auf ein Objekt auf dem verwalteten Heap verweist.  
  
 Die Objekt-IDs zurückgegebenes `RootReferences2` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann. Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen. Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und können problemlos geprüft werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
