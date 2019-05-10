---
title: ICorProfilerInfo::SetILInstrumentedCodeMap-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ec0f986efe24b0b69df9d2ecd93335f7ac5db28
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606631"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="ac3fd-102">ICorProfilerInfo::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="ac3fd-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="ac3fd-103">Legt eine Code Map für die angegebene Funktion, die mit der angegebenen Microsoft intermediate Language (MSIL)-Zuordnungseinträge fest.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac3fd-104">In .NET Framework, Version 2.0, Aufrufen von `SetILInstrumentedCodeMap` auf eine `FunctionID` , dass alle Instanzen dieser Funktion in der Anwendungsdomäne darstellt, die eine generische Funktion in einer bestimmten Anwendungsdomäne auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3fd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac3fd-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac3fd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac3fd-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ac3fd-107">[in] Die ID der Funktion für die die Code Map festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="ac3fd-108">[in] Ein boolescher Wert, der angibt, ob der Aufruf der `SetILInstrumentedCodeMap` Methode ist die erste für einen bestimmten `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="ac3fd-109">Legen Sie `fStartJit` zu `true` im ersten Aufruf von `SetILInstrumentedCodeMap` für einen angegebenen `FunctionID`, und `false` danach.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="ac3fd-110">[in] Die Anzahl der Elemente in der `cILMapEntries` Array.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="ac3fd-111">[in] Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac3fd-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac3fd-112">Remarks</span></span>  
 <span data-ttu-id="ac3fd-113">Ein Profiler fügt häufig die Anweisungen im Quellcode einer Methode zum Instrumentieren von dieser Methode (z. B. zu benachrichtigen, wenn eine Zeile für die angegebene Quelle erreicht wird).</span><span class="sxs-lookup"><span data-stu-id="ac3fd-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="ac3fd-114">`SetILInstrumentedCodeMap` ermöglicht einen Profiler, die ursprünglichen MSIL-Anweisungen zu den neuen Speicherorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="ac3fd-115">Ein Profiler können die [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) Methode, um den ursprünglichen MSIL-Offset für einen bestimmten Offset des systemeigenen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="ac3fd-116">Der Debugger geht davon aus, dass jeder Alter Offset auf einen MSIL-offset innerhalb der ursprünglichen, unveränderten MSIL-Code verweist, und jeder neuer Offset auf den MSIL-Offset innerhalb der neuen, instrumentierten Code verweist.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="ac3fd-117">Die Zuordnung muss in aufsteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="ac3fd-118">Führen Sie für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="ac3fd-118">For stepping to work properly, follow these guidelines:</span></span>  
  
- <span data-ttu-id="ac3fd-119">Keine neu instrumentierten MSIL-Code an.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-119">Do not reorder instrumented MSIL code.</span></span>  
  
- <span data-ttu-id="ac3fd-120">Entfernen Sie den ursprünglichen MSIL-Code nicht.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-120">Do not remove the original MSIL code.</span></span>  
  
- <span data-ttu-id="ac3fd-121">Enthalten Sie Einträge für die Sequenzpunkte über die Programmdatenbankdatei (PDB) werden in der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="ac3fd-122">Die Zuordnung wird nicht fehlenden Einträge interpoliert.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="ac3fd-123">Betrachten Sie daher in der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ac3fd-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="ac3fd-124">(0 alt ist, 0 neue)</span><span class="sxs-lookup"><span data-stu-id="ac3fd-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="ac3fd-125">(5 alt ist, 10 neue)</span><span class="sxs-lookup"><span data-stu-id="ac3fd-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="ac3fd-126">(9 ALT ist, 20 neue)</span><span class="sxs-lookup"><span data-stu-id="ac3fd-126">(9 old, 20 new)</span></span>  
  
    - <span data-ttu-id="ac3fd-127">Ein Alter Offset von 0, 1, 2, 3 oder 4 wird zum neuen Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    - <span data-ttu-id="ac3fd-128">Ein Alter Offset von 5, 6, 7 oder 8 wird zum neuen Offset 10 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    - <span data-ttu-id="ac3fd-129">Ein Alter Offset des 9 oder höher wird zum neuen Offset 20 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    - <span data-ttu-id="ac3fd-130">Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 werden alte Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    - <span data-ttu-id="ac3fd-131">Alte Offset 5 wird ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    - <span data-ttu-id="ac3fd-132">Ein neuer Offset von 20 oder höher werden alte Offset 9 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac3fd-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac3fd-133">Requirements</span></span>  
 <span data-ttu-id="ac3fd-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac3fd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3fd-135">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac3fd-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac3fd-136">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac3fd-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac3fd-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3fd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3fd-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac3fd-138">See also</span></span>

- [<span data-ttu-id="ac3fd-139">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac3fd-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
