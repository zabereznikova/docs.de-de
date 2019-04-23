---
title: ICorProfilerCallback2::RootReferences2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09616243aef272be041573864effd25017cc65c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082151"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2-Methode
Benachrichtigt den Profiler über Root-verweisen an, nach eine Garbagecollection aufgetreten ist. Diese Methode ist eine Erweiterung von der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cRootRefs`  
 [in] Die Anzahl der Elemente in der `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays.  
  
 `rootRefIds`  
 [in] Ein Array von Objekt-IDs, von denen jeder entweder ein statisches Objekt oder ein Objekt im Stapel verweist. Elemente in der `rootKinds` Angaben zum Klassifizieren der entsprechenden Elemente im Array der `rootRefIds` Array.  
  
 `rootKinds`  
 [in] Ein Array von [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) Werte, die den Typ der Garbage Collection-Stamm angeben.  
  
 `rootFlags`  
 [in] Ein Array von [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) Werte, die die Eigenschaften einer Garbage Collection-Stamm zu beschreiben.  
  
 `rootIds`  
 [in] Ein Array von UINT_PTR Werten, die in eine ganze Zahl, die zusätzliche Informationen über die Garbage Collection-Stamm, abhängig vom Wert enthält die `rootKinds` Parameter.  
  
 Wenn der Typ des Stamms eines Stapels ist, ist der Stamm-ID für die Funktion, die die Variable enthält. Wenn die Stamm-ID 0 ist, ist die Funktion eine unbenannte Funktion, die intern für die CLR ist. Wenn der Typ des Stamms ein Handle ist, ist der Stamm-ID für die Garbage Collection-Handle. Für die anderen Stammreferenztypen die ID ist ein nicht transparenter Wert und ignoriert werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays sind parallele Arrays. D. h. `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, und `rootIds[i]` betreffen alle den gleichen Stamm.  
  
 Beide `RootReferences` und `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise eine Methode oder die andere, aber nicht beides, da die Informationen in übergeben `RootReferences2` ist eine Obermenge der, die übergebene `RootReferences`.  
  
 Es ist möglich, dass Einträge in `rootRefIds` gleich 0 (null), das bedeutet, dass der entsprechende Stammverweis null ist, und nicht auf ein Objekt auf dem verwalteten Heap verweist.  
  
 Die Objekt-IDs von zurückgegebenen `RootReferences2` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann. Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen. Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und problemlos überprüft werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
