---
title: ICorProfilerInfo2::GetGenerationBounds-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 2e6e3a6432d6568532a5f5b9676b5f130eb83d0b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502886"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="47863-102">ICorProfilerInfo2::GetGenerationBounds-Methode</span><span class="sxs-lookup"><span data-stu-id="47863-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="47863-103">Ruft die Arbeitsspeicherbereiche ab, die Segmente des Heaps sind, aus dem sich die verschiedenen Garbage Collection-Generationen zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="47863-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47863-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47863-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47863-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47863-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="47863-106">[in] Die Anzahl der Elemente, die der Aufrufer dem `ranges`-Array zugeordnet hat.</span><span class="sxs-lookup"><span data-stu-id="47863-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="47863-107">[out] Ein Zeiger auf eine ganze Zahl, die die Gesamtzahl der Bereiche angibt, von denen einige oder alle im `ranges`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="47863-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="47863-108">vorgenommen Ein Array von [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) Strukturen, von denen jedes einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation beschreibt, die Garbage Collection wird.</span><span class="sxs-lookup"><span data-stu-id="47863-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47863-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="47863-109">Remarks</span></span>  
 <span data-ttu-id="47863-110">Die `GetGenerationBounds`-Methode kann von jedem Profilerrückruf aufgerufen werden, solange die Garbage Collection nicht durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47863-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="47863-111">Die meisten Generationenverschiebungen finden während der Garbage Collections statt.</span><span class="sxs-lookup"><span data-stu-id="47863-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="47863-112">Generationen können zwischen Auflistungen anwachsen, verschieben sich im Allgemeinen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="47863-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="47863-113">Deshalb befinden sich die interessantesten Positionen zum Aufrufen von `GetGenerationBounds` in `ICorProfilerCallback2::GarbageCollectionStarted` und `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="47863-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="47863-114">Während des Programmstarts werden einige Objekte in der Regel in den Generationen 3 und 0 von der Common Language Runtime (CLR) selbst zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="47863-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="47863-115">Daher enthalten diese Generationen zu dem Zeitpunkt, an dem der verwaltete Code die Ausführung startet, bereits Objekte.</span><span class="sxs-lookup"><span data-stu-id="47863-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="47863-116">Die Generationen 1 und 2 sind normalerweise (bis auf vom Garbage Collector generierte Dummyobjekte) leer.</span><span class="sxs-lookup"><span data-stu-id="47863-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="47863-117">(Die Größe der Dummyobjekte beträgt 12 Bytes in 32-Bit-Implementierungen der CLR; die Größe ist in 64-Bit-Implementierungen größer.) Es können auch Bereiche der Generation 2 angezeigt werden, die sich innerhalb von Modulen befinden, die vom Native Image Generator (Ngen. exe) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="47863-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="47863-118">In diesem Fall sind die Objekte in Generation 2 fixierte *Objekte*, die zugeordnet werden, wenn "ngen. exe" statt der Garbage Collector ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47863-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="47863-119">Diese Funktion verwendet vom Aufrufer reservierte Puffer.</span><span class="sxs-lookup"><span data-stu-id="47863-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47863-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="47863-120">Requirements</span></span>  
 <span data-ttu-id="47863-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47863-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47863-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47863-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47863-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47863-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47863-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47863-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47863-125">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="47863-125">See also</span></span>

- [<span data-ttu-id="47863-126">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47863-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="47863-127">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47863-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="47863-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="47863-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="47863-129">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="47863-129">Profiling</span></span>](index.md)
