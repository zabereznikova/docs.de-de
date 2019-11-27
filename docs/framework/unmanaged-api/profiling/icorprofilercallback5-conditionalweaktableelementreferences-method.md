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
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="bc3c3-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3c3-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>

<span data-ttu-id="bc3c3-103">Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-103">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc3c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc3c3-104">Syntax</span></span>

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a><span data-ttu-id="bc3c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc3c3-105">Parameters</span></span>

`cRootRefs`\
<span data-ttu-id="bc3c3-106">[in] Die Anzahl der Elemente in `keyRefIds`-, in `valueRefIds`- und `rootIds`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-106">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>

`keyRefIds`\
<span data-ttu-id="bc3c3-107">[in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das primäre Element im abhängigen Handlepaar enthält.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-107">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>

`valueRefIds`\
<span data-ttu-id="bc3c3-108">[in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das sekundäre Element im abhängigen Handlepaar enthält.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-108">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="bc3c3-109">(`keyRefIds[i]` hält `valueRefIds[i]` aktiv.)</span><span class="sxs-lookup"><span data-stu-id="bc3c3-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>

`rootIds`\
<span data-ttu-id="bc3c3-110">[in] Ein Array von `GCHandleID`-Werten, die auf eine ganze Zahl zeigen, die zusätzliche Informationen über den Garbage Collection-Stamm enthält.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-110">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>

<span data-ttu-id="bc3c3-111">Keine `ObjectID`-Werte, die von der `ConditionalWeakTableElementReferences`-Methode zurückgegeben werden, sind während des Rückrufs selbst gültig, da der Garbage Collector möglicherweise gerade Objekten von alten an neue Speicherorte verschiebt.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-111">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="bc3c3-112">Deshalb sollten Profiler nicht versuchen, Objekte während eines `ConditionalWeakTableElementReferences`-Aufrufs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-112">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="bc3c3-113">Bei `GarbageCollectionFinished` wurden alle Objekte zu den neuen Speicherorten verschoben, und die Überprüfung kann ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-113">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>

## <a name="example"></a><span data-ttu-id="bc3c3-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc3c3-114">Example</span></span>

<span data-ttu-id="bc3c3-115">Im folgenden Codebeispiel wird veranschaulicht, wie [ICorProfilerCallback5](icorprofilercallback5-interface.md) implementiert und diese Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-115">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="bc3c3-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc3c3-116">Remarks</span></span>

<span data-ttu-id="bc3c3-117">Ein Profiler für die .NET Framework 4,5 oder höhere Versionen implementiert die [ICorProfilerCallback5](icorprofilercallback5-interface.md) -Schnittstelle und zeichnet die von der `ConditionalWeakTableElementReferences`-Methode angegebenen Abhängigkeiten auf.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-117">A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="bc3c3-118">`ICorProfilerCallback5` bietet den gesamten Satz an Abhängigkeiten zwischen Live Objekten, die durch `ConditionalWeakTable` Einträge dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="bc3c3-119">Diese Abhängigkeiten und die Element Feldverweise, die von der [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) -Methode angegeben werden, ermöglichen einem verwalteten Profiler das Generieren des vollständigen Objekt Diagramms von Live-Objekten.</span><span class="sxs-lookup"><span data-stu-id="bc3c3-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc3c3-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc3c3-120">Requirements</span></span>

<span data-ttu-id="bc3c3-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3c3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="bc3c3-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc3c3-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="bc3c3-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3c3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bc3c3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc3c3-124">See also</span></span>

- [<span data-ttu-id="bc3c3-125">ICorProfilerCallback5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc3c3-125">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)
