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
ms.openlocfilehash: a9ce9a7a56847efcadf09924ffc56c41f20a1c58
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865726"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2-Methode
Benachrichtigt den Profiler über Stamm Verweise, nachdem ein Garbage Collection aufgetreten ist. Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `cRootRefs`  
 in Die Anzahl der Elemente in den Arrays "`rootRefIds`", "`rootKinds`", "`rootFlags`" und "`rootIds`".  
  
 `rootRefIds`  
 in Ein Array von Objekt-IDs, von denen jedes entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist. Elemente im `rootKinds` Arrays enthalten Informationen, um die entsprechenden Elemente im `rootRefIds` Array zu klassifizieren.  
  
 `rootKinds`  
 in Ein Array von [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) Werten, die den Typ des Garbage Collection Stamms angeben.  
  
 `rootFlags`  
 in Ein Array von [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) Werten, die die Eigenschaften eines Garbage Collection Stamms beschreiben.  
  
 `rootIds`  
 in Ein Array von UINT_PTR-Werten, die auf eine ganze Zahl zeigen, die abhängig vom Wert des `rootKinds`-Parameters Weitere Informationen über den Garbage Collection Stamm enthält.  
  
 Wenn der Typ des Stamms ein Stapel ist, ist die Stamm-ID für die Funktion, die die Variable enthält. Wenn diese Stamm-ID 0 ist, handelt es sich bei der Funktion um eine unbenannte Funktion, die für die CLR intern ist. Wenn der Typ des Stamms ein Handle ist, ist die Stamm-ID für das Garbage Collection Handle. Bei den anderen Stamm Typen ist die ID ein nicht transparenter Wert und sollte ignoriert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `rootRefIds`-, `rootKinds`-, `rootFlags`-und `rootIds` Arrays sind parallele Arrays. Das heißt, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`und `rootIds[i]` betreffen alle denselben Stamm.  
  
 Sowohl `RootReferences` als auch `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise eine oder die andere Methode, aber nicht beides, da die in `RootReferences2` übergebenen Informationen eine supermenge von sind, die `RootReferences`übergebenen ist.  
  
 Es ist möglich, dass Einträge in `rootRefIds` NULL sind. Dies impliziert, dass der entsprechende Stamm Verweis null ist und nicht auf ein Objekt im verwalteten Heap verweist.  
  
 Die Objekt-IDs, die von `RootReferences2` zurückgegeben werden, sind während des Rückrufs nicht gültig, da die Garbage Collection möglicherweise in der Mitte des Verschiebens von Objekten von alten Adressen zu neuen Adressen liegt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
