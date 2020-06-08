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
ms.openlocfilehash: 2ce58113f40c8eb67a89b6ab6c9bb8f755975bd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499752"
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
  
## <a name="parameters"></a>Parameter  
 `cRootRefs`  
 in Die Anzahl der Elemente in den `rootRefIds` `rootKinds` Arrays,, `rootFlags` und `rootIds` .  
  
 `rootRefIds`  
 in Ein Array von Objekt-IDs, von denen jedes entweder auf ein statisches Objekt oder auf ein Objekt im Stapel verweist. Elemente im `rootKinds` Array stellen Informationen bereit, um die entsprechenden Elemente im Array zu klassifizieren `rootRefIds` .  
  
 `rootKinds`  
 in Ein Array von [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) Werten, die den Typ des Garbage Collection Stamms angeben.  
  
 `rootFlags`  
 in Ein Array von [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) Werten, die die Eigenschaften eines Garbage Collection Stamms beschreiben.  
  
 `rootIds`  
 in Ein Array von UINT_PTR Werten, die auf eine ganze Zahl zeigen, die je nach dem Wert des-Parameters Weitere Informationen über den Garbage Collection Stamm enthält `rootKinds` .  
  
 Wenn der Typ des Stamms ein Stapel ist, ist die Stamm-ID für die Funktion, die die Variable enthält. Wenn diese Stamm-ID 0 ist, handelt es sich bei der Funktion um eine unbenannte Funktion, die für die CLR intern ist. Wenn der Typ des Stamms ein Handle ist, ist die Stamm-ID für das Garbage Collection Handle. Bei den anderen Stamm Typen ist die ID ein nicht transparenter Wert und sollte ignoriert werden.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `rootRefIds` `rootKinds` Arrays,, `rootFlags` und `rootIds` sind parallele Arrays. Das heißt, `rootRefIds[i]` , `rootKinds[i]` , `rootFlags[i]` und `rootIds[i]` betreffen alle denselben Stamm.  
  
 `RootReferences`Und `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen. Profiler implementieren normalerweise eine oder die andere Methode, aber nicht beides, da die übergebenen Informationen `RootReferences2` eine übergeordnete Menge von ist, die in übergebenen ist `RootReferences` .  
  
 Es ist möglich, dass Einträge in `rootRefIds` NULL sind. Dies impliziert, dass der entsprechende Stamm Verweis null ist und nicht auf ein Objekt im verwalteten Heap verweist.  
  
 Die Objekt-IDs, die von zurückgegeben werden `RootReferences2` , sind während des Rückrufs selbst nicht gültig, da die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten von alten Adressen zu neuen Adressen liegt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectionabgeschlossene](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wurden alle Objekte an Ihre neuen Speicherorte verschoben und können sicher überprüft werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
