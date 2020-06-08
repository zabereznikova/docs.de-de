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
ms.openlocfilehash: 17fbc99b30921f795c1f7ff882ec73432aade8c6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499245"
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

Im folgenden Codebeispiel wird veranschaulicht, wie [ICorProfilerCallback5](icorprofilercallback5-interface.md) implementiert und diese Methode verwendet wird.

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

## <a name="remarks"></a>Bemerkungen

Ein Profiler für die .NET Framework 4,5 oder höhere Versionen implementiert die [ICorProfilerCallback5](icorprofilercallback5-interface.md) -Schnittstelle und zeichnet die von der-Methode angegebenen Abhängigkeiten auf `ConditionalWeakTableElementReferences` . `ICorProfilerCallback5`stellt den gesamten Satz von Abhängigkeiten zwischen Live Objekten bereit, die durch-Einträge dargestellt werden `ConditionalWeakTable` . Diese Abhängigkeiten und die Element Feldverweise, die von der [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) -Methode angegeben werden, ermöglichen einem verwalteten Profiler das Generieren des vollständigen Objekt Diagramms von Live-Objekten.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback5-Schnittstelle](icorprofilercallback5-interface.md)
