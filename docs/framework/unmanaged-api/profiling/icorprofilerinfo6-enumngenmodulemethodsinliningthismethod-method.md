---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568152"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="c786c-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span><span class="sxs-lookup"><span data-stu-id="c786c-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="c786c-103">[Wird nur in der .NET Framework 4.6 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c786c-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="c786c-104">Gibt einen Enumerator für alle Methoden, die in einem bestimmten NGen-Modul und Inline einer bestimmten Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c786c-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c786c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c786c-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c786c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c786c-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="c786c-107">[in] Der Bezeichner des NGen-Modul.</span><span class="sxs-lookup"><span data-stu-id="c786c-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="c786c-108">[in] Der Bezeichner eines Moduls, das definiert `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="c786c-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="c786c-109">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c786c-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="c786c-110">[in] Der Bezeichner einer Inline-Methode.</span><span class="sxs-lookup"><span data-stu-id="c786c-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="c786c-111">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c786c-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="c786c-112">[out] Ein Flag, das angibt, ob `ppEnum` enthält alle Methoden, die inlineersetzung eine bestimmte Methode.</span><span class="sxs-lookup"><span data-stu-id="c786c-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="c786c-113">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c786c-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="c786c-114">[out] Ein Zeiger auf die Adresse eines Enumerators</span><span class="sxs-lookup"><span data-stu-id="c786c-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c786c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c786c-115">Remarks</span></span>  
 <span data-ttu-id="c786c-116">`inlineeModuleId` und `inlineeMethodId` zusammen bilden den vollständigen Bezeichner für die Methode, die intern sein können.</span><span class="sxs-lookup"><span data-stu-id="c786c-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="c786c-117">Nehmen wir beispielsweise an das Modul `A` definiert eine Methode `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="c786c-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="c786c-118">und das Modul Bdefines `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="c786c-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="c786c-119">Ermöglicht darüber hinaus vorausgesetzt, die `Fancy.AddTwice` wird der Aufruf zum `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="c786c-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="c786c-120">Ein Profiler kann dieser Enumerator verwenden, finden Sie in Modul B die Inline definiert alle Methoden `Simple.Add`, und das Ergebnis würde auflisten `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="c786c-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="c786c-121">`inlineeModuleId` Der Bezeichner des Moduls `A`, und `inlineeeMethodId` ist der Bezeichner des `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="c786c-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="c786c-122">Wenn `incompleteData` ist nach der Funktion "true" zurückgibt, der Enumerator enthält nicht alle Methoden, die inlineersetzung eine bestimmte Methode.</span><span class="sxs-lookup"><span data-stu-id="c786c-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="c786c-123">Dies kann auftreten, wenn ein oder direkte oder indirekte Abhängigkeiten des Inliners-Moduls wurde noch nicht getan haben geladen.</span><span class="sxs-lookup"><span data-stu-id="c786c-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="c786c-124">Wenn ein Profiler die genaue Daten benötigt, sollte es später noch Mal, wenn weitere Module, vorzugsweise auf jedem Modul laden geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c786c-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="c786c-125">Die `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen umgehen für ReJIT inlining.</span><span class="sxs-lookup"><span data-stu-id="c786c-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="c786c-126">ReJIT kann es sich um einen Profiler, ändern Sie die Implementierung einer Methode, und klicken Sie dann für sie neuen Code erstellen, im laufenden Betrieb.</span><span class="sxs-lookup"><span data-stu-id="c786c-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="c786c-127">Wir könnten z. B. ändern `Simple.Add` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c786c-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="c786c-128">Aber da `Fancy.AddTwice` hat bereits inline `Simple.Add`, es verfügt auch weiterhin über das gleiche Verhalten wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="c786c-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="c786c-129">Zur Umgehung dieser Einschränkung der Aufrufer muss für alle Methoden in allen Modulen, Inline suchen `Simple.Add` und `ICorProfilerInfo5::RequestRejit` auf jede dieser Methoden.</span><span class="sxs-lookup"><span data-stu-id="c786c-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="c786c-130">Wenn die Methoden neu kompilierten sind, müssen sie das neue Verhalten der `Simple.Add` anstatt das alte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="c786c-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c786c-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c786c-131">Requirements</span></span>  
 <span data-ttu-id="c786c-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c786c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c786c-133">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c786c-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c786c-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c786c-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c786c-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c786c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c786c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c786c-136">See also</span></span>
- [<span data-ttu-id="c786c-137">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c786c-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
