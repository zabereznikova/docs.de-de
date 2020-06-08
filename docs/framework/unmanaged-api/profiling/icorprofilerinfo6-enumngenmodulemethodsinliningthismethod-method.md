---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 8ed3f305deceacb976aeff994db1588f9e1ce1fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495527"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="a47b9-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="a47b9-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="a47b9-103">Gibt einen Enumerator für alle Methoden zurück, die in einem angegebenen ngen-Modul definiert sind, und Inline eine angegebene Methode.</span><span class="sxs-lookup"><span data-stu-id="a47b9-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="a47b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a47b9-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="a47b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a47b9-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="a47b9-106">in Der Bezeichner eines ngen-Moduls.</span><span class="sxs-lookup"><span data-stu-id="a47b9-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="a47b9-107">in Der Bezeichner eines Moduls, das definiert `inlineeMethodId` .</span><span class="sxs-lookup"><span data-stu-id="a47b9-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="a47b9-108">Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="a47b9-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="a47b9-109">in Der Bezeichner einer Inline Methode.</span><span class="sxs-lookup"><span data-stu-id="a47b9-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="a47b9-110">Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="a47b9-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="a47b9-111">vorgenommen Ein Flag, das angibt, ob `ppEnum` alle Methoden enthält, die eine bestimmte Methode Inlining.</span><span class="sxs-lookup"><span data-stu-id="a47b9-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="a47b9-112">Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="a47b9-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="a47b9-113">vorgenommen Ein Zeiger auf die Adresse eines Enumerators.</span><span class="sxs-lookup"><span data-stu-id="a47b9-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="a47b9-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a47b9-114">Remarks</span></span>

<span data-ttu-id="a47b9-115">`inlineeModuleId`und `inlineeMethodId` bilden den vollständigen Bezeichner für die Methode, die möglicherweise Inline ist.</span><span class="sxs-lookup"><span data-stu-id="a47b9-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="a47b9-116">Nehmen Sie beispielsweise an, das Modul `A` definiert eine Methode `Simple.Add` :</span><span class="sxs-lookup"><span data-stu-id="a47b9-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="a47b9-117">und Modul B definiert Folgendes `Fancy.AddTwice` :</span><span class="sxs-lookup"><span data-stu-id="a47b9-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="a47b9-118">Außerdem wird davon ausgegangen, dass den-Befehl `Fancy.AddTwice` in den Zeilen umgibt `SimpleAdd` .</span><span class="sxs-lookup"><span data-stu-id="a47b9-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="a47b9-119">Ein Profiler kann mit diesem Enumerator alle in Modul B definierten Methoden suchen, die Inline `Simple.Add` sind, und das Ergebnis würde aufzählen `AddTwice` .</span><span class="sxs-lookup"><span data-stu-id="a47b9-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="a47b9-120">`inlineeModuleId`der Bezeichner des Moduls `A` , und `inlineeMethodId` ist der Bezeichner von `Simple.Add(int a, int b)` .</span><span class="sxs-lookup"><span data-stu-id="a47b9-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="a47b9-121">Wenn den Wert `incompleteData` true hat, nachdem die Funktion zurückgegeben wurde, enthält der Enumerator nicht alle Methoden, die eine bestimmte Methode Inlining enthalten.</span><span class="sxs-lookup"><span data-stu-id="a47b9-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="a47b9-122">Dies kann vorkommen, wenn eine oder mehrere direkte oder indirekte Abhängigkeiten des Inliners-Moduls noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="a47b9-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="a47b9-123">Wenn ein Profiler genaue Daten benötigt, sollte er später wiederholt werden, wenn mehr Module geladen werden, vorzugsweise bei jedem Modul Ladevorgang.</span><span class="sxs-lookup"><span data-stu-id="a47b9-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="a47b9-124">Die- `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen beim Inlining für ReJIT zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="a47b9-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="a47b9-125">ReJIT ermöglicht einem Profiler, die Implementierung einer Methode zu ändern und dann im Handumdrehen neuen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a47b9-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="a47b9-126">Beispielsweise können wir `Simple.Add` wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="a47b9-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="a47b9-127">Da jedoch `Fancy.AddTwice` bereits Inline ist `Simple.Add` , weist es weiterhin das gleiche Verhalten wie zuvor auf.</span><span class="sxs-lookup"><span data-stu-id="a47b9-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="a47b9-128">Um diese Einschränkung zu umgehen, muss der Aufrufer alle Methoden in allen Modulen suchen, die Inline sind `Simple.Add` und für `ICorProfilerInfo5::RequestRejit` jede dieser Methoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a47b9-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="a47b9-129">Wenn die Methoden erneut kompiliert werden, verfügen Sie über das neue Verhalten von `Simple.Add` anstelle des alten Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="a47b9-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="a47b9-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a47b9-130">Requirements</span></span>

<span data-ttu-id="a47b9-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47b9-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a47b9-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a47b9-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a47b9-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47b9-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a47b9-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47b9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a47b9-135">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a47b9-135">See also</span></span>

- [<span data-ttu-id="a47b9-136">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47b9-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
