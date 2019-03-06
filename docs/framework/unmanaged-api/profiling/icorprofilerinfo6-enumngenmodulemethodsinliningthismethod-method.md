---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365320"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="1e523-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span><span class="sxs-lookup"><span data-stu-id="1e523-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="1e523-103">Gibt einen Enumerator für alle Methoden, die in einem bestimmten NGen-Modul und Inline einer bestimmten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1e523-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e523-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e523-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="1e523-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e523-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="1e523-106">[in] Der Bezeichner des NGen-Modul.</span><span class="sxs-lookup"><span data-stu-id="1e523-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="1e523-107">[in] Der Bezeichner eines Moduls, das definiert `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="1e523-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="1e523-108">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1e523-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="1e523-109">[in] Der Bezeichner einer Inline-Methode.</span><span class="sxs-lookup"><span data-stu-id="1e523-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="1e523-110">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1e523-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="1e523-111">[out] Ein Flag, das angibt, ob `ppEnum` enthält alle Methoden, die inlineersetzung eine bestimmte Methode.</span><span class="sxs-lookup"><span data-stu-id="1e523-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="1e523-112">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1e523-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="1e523-113">[out] Ein Zeiger auf die Adresse eines Enumerators</span><span class="sxs-lookup"><span data-stu-id="1e523-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="1e523-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e523-114">Remarks</span></span>

<span data-ttu-id="1e523-115">`inlineeModuleId` und `inlineeMethodId` zusammen bilden den vollständigen Bezeichner für die Methode, die intern sein können.</span><span class="sxs-lookup"><span data-stu-id="1e523-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="1e523-116">Nehmen wir beispielsweise an das Modul `A` definiert eine Methode `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="1e523-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="1e523-117">Modul B definiert `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="1e523-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="1e523-118">Ermöglicht darüber hinaus vorausgesetzt, die `Fancy.AddTwice` wird der Aufruf zum `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="1e523-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="1e523-119">Ein Profiler kann dieser Enumerator verwenden, finden Sie in Modul B die Inline definiert alle Methoden `Simple.Add`, und das Ergebnis würde auflisten `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="1e523-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="1e523-120">`inlineeModuleId` Der Bezeichner des Moduls `A`, und `inlineeMethodId` ist der Bezeichner des `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="1e523-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="1e523-121">Wenn `incompleteData` ist nach der Funktion "true" zurückgibt, der Enumerator enthält nicht alle Methoden, die inlineersetzung eine bestimmte Methode.</span><span class="sxs-lookup"><span data-stu-id="1e523-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="1e523-122">Dies kann auftreten, wenn ein oder direkte oder indirekte Abhängigkeiten des Inliners-Moduls wurde noch nicht getan haben geladen.</span><span class="sxs-lookup"><span data-stu-id="1e523-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="1e523-123">Wenn ein Profiler die genaue Daten benötigt, sollte es später noch Mal, wenn weitere Module, vorzugsweise auf jedem Modul laden geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1e523-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="1e523-124">Die `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen umgehen für ReJIT inlining.</span><span class="sxs-lookup"><span data-stu-id="1e523-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="1e523-125">ReJIT kann es sich um einen Profiler, ändern Sie die Implementierung einer Methode, und klicken Sie dann für sie neuen Code erstellen, im laufenden Betrieb.</span><span class="sxs-lookup"><span data-stu-id="1e523-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="1e523-126">Wir könnten z. B. ändern `Simple.Add` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1e523-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="1e523-127">Aber da `Fancy.AddTwice` hat bereits inline `Simple.Add`, es verfügt auch weiterhin über das gleiche Verhalten wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="1e523-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="1e523-128">Zur Umgehung dieser Einschränkung der Aufrufer muss für alle Methoden in allen Modulen, Inline suchen `Simple.Add` und `ICorProfilerInfo5::RequestRejit` auf jede dieser Methoden.</span><span class="sxs-lookup"><span data-stu-id="1e523-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="1e523-129">Wenn die Methoden neu kompilierten sind, müssen sie das neue Verhalten der `Simple.Add` anstatt das alte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="1e523-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e523-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e523-130">Requirements</span></span>

<span data-ttu-id="1e523-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e523-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1e523-132">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e523-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1e523-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e523-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1e523-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e523-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1e523-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e523-135">See also</span></span>

- [<span data-ttu-id="1e523-136">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e523-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)