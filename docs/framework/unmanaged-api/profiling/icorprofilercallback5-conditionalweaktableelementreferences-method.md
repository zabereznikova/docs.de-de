---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
ms.openlocfilehash: ad721d28f6a7dc6ae0370ce10178990cb02fb9f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430054"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>ICorProfilerCallback5::ConditionalWeakTableElementReferences-Methode

Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a>Parameter

`cRootRefs`\
[in] Die Anzahl der Elemente in `keyRefIds`-, in `valueRefIds`- und `rootIds`-Arrays.

`keyRefIds`\
[in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das primäre Element im abhängigen Handlepaar enthält.

`valueRefIds`\
[in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das sekundäre Element im abhängigen Handlepaar enthält. (`keyRefIds[i]` hält `valueRefIds[i]` aktiv.)

`rootIds`\
[in] Ein Array von `GCHandleID`-Werten, die auf eine ganze Zahl zeigen, die zusätzliche Informationen über den Garbage Collection-Stamm enthält.

Keine `ObjectID`-Werte, die von der `ConditionalWeakTableElementReferences`-Methode zurückgegeben werden, sind während des Rückrufs selbst gültig, da der Garbage Collector möglicherweise gerade Objekten von alten an neue Speicherorte verschiebt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `ConditionalWeakTableElementReferences`-Aufrufs zu überprüfen. Bei `GarbageCollectionFinished` wurden alle Objekte zu den neuen Speicherorten verschoben, und die Überprüfung kann ausgeführt werden.

## <a name="example"></a>Beispiel

The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a>Hinweise

A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method. `ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries. These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback5-Schnittstelle](icorprofilercallback5-interface.md)
