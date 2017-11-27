---
title: ICorProfilerInfo::SetILInstrumentedCodeMap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 35c87b98a8e0c02ab6f4bca7a4f7a16ff6839c6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="eef4f-102">ICorProfilerInfo::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="eef4f-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="eef4f-103">Legt eine Code Map für die angegebene Funktion mithilfe der festgelegten Zuordnungseinträge der Microsoft intermediate Language (MSIL) fest.</span><span class="sxs-lookup"><span data-stu-id="eef4f-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eef4f-104">In .NET Framework, Version 2.0, Aufrufen von `SetILInstrumentedCodeMap` auf eine `FunctionID` , dass alle Instanzen dieser Funktion in der Anwendungsdomäne darstellt, die eine generische Funktion in einer bestimmten Anwendungsdomäne beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="eef4f-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef4f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eef4f-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eef4f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eef4f-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="eef4f-107">[in] Die ID der Funktion für die die Code Map festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eef4f-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="eef4f-108">[in] Ein boolescher Wert, der angibt, ob der Aufruf der `SetILInstrumentedCodeMap` Methode ist die erste für einen bestimmten `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="eef4f-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="eef4f-109">Festgelegt `fStartJit` auf `true` im ersten Aufruf von `SetILInstrumentedCodeMap` für einen bestimmten `FunctionID`, und `false` danach.</span><span class="sxs-lookup"><span data-stu-id="eef4f-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="eef4f-110">[in] Die Anzahl der Elemente in der `cILMapEntries` Array.</span><span class="sxs-lookup"><span data-stu-id="eef4f-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="eef4f-111">[in] Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.</span><span class="sxs-lookup"><span data-stu-id="eef4f-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef4f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eef4f-112">Remarks</span></span>  
 <span data-ttu-id="eef4f-113">Ein Profiler fügt oft Anweisungen innerhalb des Quellcodes einer Methode um Instrumentieren Ermittlungsmethode (z. B. zu benachrichtigen, wenn eine Zeile für die angegebene Quelle erreicht ist).</span><span class="sxs-lookup"><span data-stu-id="eef4f-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="eef4f-114">`SetILInstrumentedCodeMap`ermöglicht einen Profiler an die neuen Speicherorte die ursprünglichen MSIL-Anweisungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="eef4f-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="eef4f-115">Ein Profiler können Sie die [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) Methode, um den ursprünglichen MSIL-Offset für einen bestimmten systemeigenen Offset abrufen.</span><span class="sxs-lookup"><span data-stu-id="eef4f-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="eef4f-116">Der Debugger wird davon ausgegangen, dass jeder Alter Offset auf einen MSIL-offset innerhalb der ursprünglichen, unveränderten MSIL-Code verweist, und dass jeder neuer Offset auf den MSIL-Offset innerhalb der neuen, instrumentierten Code verweist.</span><span class="sxs-lookup"><span data-stu-id="eef4f-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="eef4f-117">Die Zuordnung sollte in aufsteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="eef4f-118">Beachten Sie für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eef4f-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="eef4f-119">Anordnung ändern Sie instrumentierten MSIL-Code nicht.</span><span class="sxs-lookup"><span data-stu-id="eef4f-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="eef4f-120">Entfernen Sie den ursprünglichen MSIL-Code nicht.</span><span class="sxs-lookup"><span data-stu-id="eef4f-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="eef4f-121">Schließen Sie Einträge für die Sequenzpunkte aus der Programmdatenbankdatei (PDB), in der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="eef4f-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="eef4f-122">Die Zuordnung ist nicht fehlenden Einträge interpolieren.</span><span class="sxs-lookup"><span data-stu-id="eef4f-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="eef4f-123">Der folgende Code Map wird daher angenommen:</span><span class="sxs-lookup"><span data-stu-id="eef4f-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="eef4f-124">(0 alt, 0 neu)</span><span class="sxs-lookup"><span data-stu-id="eef4f-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="eef4f-125">(5 ALT, 10 neue)</span><span class="sxs-lookup"><span data-stu-id="eef4f-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="eef4f-126">(9 ALT, 20 neu)</span><span class="sxs-lookup"><span data-stu-id="eef4f-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="eef4f-127">Ein Alter Offset von 0, 1, 2, 3 oder 4 wird dem neuen Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="eef4f-128">Ein Alter Offset von 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="eef4f-129">Ein Alter Offset von 9 oder höher werden neue Offset 20 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="eef4f-130">Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="eef4f-131">Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="eef4f-132">Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef4f-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef4f-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eef4f-133">Requirements</span></span>  
 <span data-ttu-id="eef4f-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eef4f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef4f-135">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eef4f-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eef4f-136">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eef4f-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eef4f-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef4f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef4f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eef4f-138">See Also</span></span>  
 [<span data-ttu-id="eef4f-139">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eef4f-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
