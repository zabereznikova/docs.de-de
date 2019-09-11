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
ms.openlocfilehash: 65eee2e834251817b461f1cd1debf212696d5a5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855694"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="f118b-102">ICorProfilerInfo::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="f118b-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="f118b-103">Legt einen Code Map für die angegebene Funktion mithilfe der angegebenen MSIL (Microsoft Intermediate Language)-Zuordnungs Einträge fest.</span><span class="sxs-lookup"><span data-stu-id="f118b-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="f118b-104">In der .NET Framework Version 2,0 wirkt sich `SetILInstrumentedCodeMap` das Aufrufen `FunctionID` von für eine, die eine generische Funktion in einer bestimmten Anwendungsdomäne darstellt, auf alle Instanzen dieser Funktion in der Anwendungsdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="f118b-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="f118b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f118b-105">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="f118b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f118b-106">Parameters</span></span>

`functionId`\
<span data-ttu-id="f118b-107">in Die ID der Funktion, für die die Code Map festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f118b-107">[in] The ID of the function for which to set the code map.</span></span>

`fStartJit`\
<span data-ttu-id="f118b-108">in Ein boolescher Wert, der angibt, ob der Aufrufe `SetILInstrumentedCodeMap` der-Methode der erste für eine `FunctionID`bestimmte ist.</span><span class="sxs-lookup"><span data-stu-id="f118b-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="f118b-109">Legen `fStartJit` Sie `true` auf fest `FunctionID`, wenn der `SetILInstrumentedCodeMap` erste aufgerufen wird, und anschließend `false` auf.</span><span class="sxs-lookup"><span data-stu-id="f118b-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

`cILMapEntries`\
<span data-ttu-id="f118b-110">in Die Anzahl der Elemente im `cILMapEntries` Array.</span><span class="sxs-lookup"><span data-stu-id="f118b-110">[in] The number of elements in the `cILMapEntries` array.</span></span>

`rgILMapEntries`\
<span data-ttu-id="f118b-111">in Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.</span><span class="sxs-lookup"><span data-stu-id="f118b-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="f118b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f118b-112">Remarks</span></span>

<span data-ttu-id="f118b-113">Ein Profiler fügt häufig Anweisungen innerhalb des Quellcodes einer Methode ein, um diese Methode zu instrumentieren (z. b. um zu benachrichtigen, wenn eine bestimmte Quellzeile erreicht ist).</span><span class="sxs-lookup"><span data-stu-id="f118b-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="f118b-114">`SetILInstrumentedCodeMap`ermöglicht einem Profiler, die ursprünglichen MSIL-Anweisungen ihren neuen Speicherorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f118b-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="f118b-115">Ein Profiler kann die [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) -Methode verwenden, um den ursprünglichen MSIL-Offset für einen angegebenen systemeigenen Offset zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f118b-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="f118b-116">Der Debugger geht davon aus, dass jeder alte Offset in dem ursprünglichen, nicht geänderten MSIL-Code auf einen MSIL-Offset verweist und dass jeder neue Offset auf den MSIL-Offset innerhalb des neuen, instrumentierten Codes verweist.</span><span class="sxs-lookup"><span data-stu-id="f118b-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="f118b-117">Die Zuordnung sollte in steigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="f118b-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="f118b-118">Befolgen Sie die folgenden Richtlinien, um die ordnungsgemäße Ausführung von Schritt zu</span><span class="sxs-lookup"><span data-stu-id="f118b-118">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="f118b-119">Instrumentierte MSIL-Code nicht neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="f118b-119">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="f118b-120">Entfernen Sie den ursprünglichen MSIL-Code nicht.</span><span class="sxs-lookup"><span data-stu-id="f118b-120">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="f118b-121">Fügen Sie Einträge für alle Sequenz Punkte aus der Programm Datenbankdatei (PDB) in die Zuordnung ein.</span><span class="sxs-lookup"><span data-stu-id="f118b-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="f118b-122">Fehlende Einträge werden von der Zuordnung nicht interpolieren.</span><span class="sxs-lookup"><span data-stu-id="f118b-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="f118b-123">Bei der folgenden Karte:</span><span class="sxs-lookup"><span data-stu-id="f118b-123">So, given the following map:</span></span>

  <span data-ttu-id="f118b-124">(0 alt, 0 neu)</span><span class="sxs-lookup"><span data-stu-id="f118b-124">(0 old, 0 new)</span></span>

  <span data-ttu-id="f118b-125">(5 alt, 10 neu)</span><span class="sxs-lookup"><span data-stu-id="f118b-125">(5 old, 10 new)</span></span>

  <span data-ttu-id="f118b-126">(9 alte, 20 neue)</span><span class="sxs-lookup"><span data-stu-id="f118b-126">(9 old, 20 new)</span></span>

  - <span data-ttu-id="f118b-127">Der alte Offset 0, 1, 2, 3 oder 4 wird dem neuen Offset 0 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="f118b-128">Der alte Offset 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="f118b-129">Ein Alter Offset von 9 oder höher wird dem neuen Offset 20 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="f118b-130">Der neue Offset 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="f118b-131">Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="f118b-132">Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f118b-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

<span data-ttu-id="f118b-133">In den .NET Framework 3,5 und früheren Versionen weisen Sie das `rgILMapEntries` Array zu, indem Sie die [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f118b-133">In the .NET Framework 3.5 and previous versions, you allocate the `rgILMapEntries` array by calling the [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) method.</span></span> <span data-ttu-id="f118b-134">Da die Laufzeit den Besitz dieses Speichers übernimmt, sollte der Profiler nicht versuchen, ihn freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f118b-134">Because the runtime takes ownership of this memory, the profiler should not attempt to free it.</span></span>

## <a name="requirements"></a><span data-ttu-id="f118b-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f118b-135">Requirements</span></span>

<span data-ttu-id="f118b-136">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f118b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f118b-137">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="f118b-137">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f118b-138">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f118b-138">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f118b-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f118b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f118b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f118b-140">See also</span></span>

- [<span data-ttu-id="f118b-141">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f118b-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
