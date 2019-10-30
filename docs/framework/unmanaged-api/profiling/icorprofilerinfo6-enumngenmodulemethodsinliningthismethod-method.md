---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130382"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="1b70e-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="1b70e-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="1b70e-103">Gibt einen Enumerator für alle Methoden zurück, die in einem angegebenen ngen-Modul definiert sind, und Inline eine angegebene Methode.</span><span class="sxs-lookup"><span data-stu-id="1b70e-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b70e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b70e-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="1b70e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b70e-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="1b70e-106">in Der Bezeichner eines ngen-Moduls.</span><span class="sxs-lookup"><span data-stu-id="1b70e-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="1b70e-107">in Der Bezeichner eines Moduls, das `inlineeMethodId`definiert.</span><span class="sxs-lookup"><span data-stu-id="1b70e-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="1b70e-108">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1b70e-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="1b70e-109">in Der Bezeichner einer Inline Methode.</span><span class="sxs-lookup"><span data-stu-id="1b70e-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="1b70e-110">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1b70e-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="1b70e-111">vorgenommen Ein Flag, das angibt, ob `ppEnum` alle Methoden enthält, die eine bestimmte Methode Inlining.</span><span class="sxs-lookup"><span data-stu-id="1b70e-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="1b70e-112">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1b70e-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="1b70e-113">vorgenommen Ein Zeiger auf die Adresse eines Enumerators.</span><span class="sxs-lookup"><span data-stu-id="1b70e-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="1b70e-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b70e-114">Remarks</span></span>

<span data-ttu-id="1b70e-115">`inlineeModuleId` und `inlineeMethodId` bilden den vollständigen Bezeichner für die Methode, die möglicherweise Inline ist.</span><span class="sxs-lookup"><span data-stu-id="1b70e-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="1b70e-116">Nehmen Sie beispielsweise an, Modul `A` definiert eine Methode `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="1b70e-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="1b70e-117">und Modul B definiert `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="1b70e-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="1b70e-118">Außerdem wird angenommen, dass `Fancy.AddTwice` den-Aufruf`SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="1b70e-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="1b70e-119">Ein Profiler kann diesen Enumerator verwenden, um alle in Modul B definierten Methoden zu suchen, die Inline `Simple.Add`sind, und das Ergebnis listet `AddTwice`auf.</span><span class="sxs-lookup"><span data-stu-id="1b70e-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="1b70e-120">`inlineeModuleId` ist der Bezeichner des Moduls `A`, und `inlineeMethodId` ist der Bezeichner `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="1b70e-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="1b70e-121">Wenn `incompleteData` nach der Rückgabe der Funktion true ist, enthält der Enumerator nicht alle Methoden, die eine bestimmte Methode Inlining enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b70e-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="1b70e-122">Dies kann vorkommen, wenn eine oder mehrere direkte oder indirekte Abhängigkeiten des Inliners-Moduls noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="1b70e-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="1b70e-123">Wenn ein Profiler genaue Daten benötigt, sollte er später wiederholt werden, wenn mehr Module geladen werden, vorzugsweise bei jedem Modul Ladevorgang.</span><span class="sxs-lookup"><span data-stu-id="1b70e-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="1b70e-124">Die `EnumNgenModuleMethodsInliningThisMethod`-Methode kann verwendet werden, um Einschränkungen für das Inlining für ReJIT zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="1b70e-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="1b70e-125">ReJIT ermöglicht einem Profiler, die Implementierung einer Methode zu ändern und dann im Handumdrehen neuen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b70e-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="1b70e-126">Beispielsweise können wir `Simple.Add` wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="1b70e-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="1b70e-127">Da `Fancy.AddTwice` jedoch bereits `Simple.Add`Inline ist, weist es weiterhin das gleiche Verhalten wie zuvor auf.</span><span class="sxs-lookup"><span data-stu-id="1b70e-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="1b70e-128">Um diese Einschränkung zu umgehen, muss der Aufrufer alle Methoden in allen Modulen suchen, die Inline `Simple.Add` und `ICorProfilerInfo5::RequestRejit` für jede dieser Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b70e-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="1b70e-129">Wenn die Methoden erneut kompiliert werden, haben Sie das neue Verhalten von `Simple.Add` anstelle des alten Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="1b70e-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b70e-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b70e-130">Requirements</span></span>

<span data-ttu-id="1b70e-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b70e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1b70e-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b70e-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1b70e-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b70e-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1b70e-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b70e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1b70e-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b70e-135">See also</span></span>

- [<span data-ttu-id="1b70e-136">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b70e-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
