---
title: ICorDebugILCode2::GetInstrumentedILMap-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688353"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="ebfbb-102">ICorDebugILCode2::GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="ebfbb-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>

<span data-ttu-id="ebfbb-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="ebfbb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ebfbb-104">Gibt eine Zuordnung von Profiler-instrumentierten Intermediate Language (IL) Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebfbb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebfbb-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebfbb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebfbb-106">Parameters</span></span>  

 <span data-ttu-id="ebfbb-107">cMap</span><span class="sxs-lookup"><span data-stu-id="ebfbb-107">cMap</span></span>  
 <span data-ttu-id="ebfbb-108">[in] Die Speicherkapazität für das `map`-Array.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="ebfbb-109">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="ebfbb-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="ebfbb-110">pcMap</span></span>  
 <span data-ttu-id="ebfbb-111">[out] Die Anzahl von COR_IL_MAP-Werten, die in das Zuordnungsarray geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="ebfbb-112">map</span><span class="sxs-lookup"><span data-stu-id="ebfbb-112">map</span></span>  
 <span data-ttu-id="ebfbb-113">[out] Ein Array von COR_IL_MAP-Werten, die Informationen über Zuordnungen von Profiler-instrumentierter IL zur IL der ursprünglichen Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebfbb-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebfbb-114">Remarks</span></span>  

 <span data-ttu-id="ebfbb-115">Wenn der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode festlegt, kann der Debugger diese Methode aufrufen, um die Zuordnung abzurufen und die Zuordnung intern zu verwenden, wenn IL-Offsets für Stapel Überwachungen und die Lebensdauer von Variablen berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="ebfbb-116">Wenn `cMap` 0 (null) und `pcMap` nicht **null** ist, `pcMap` wird auf die Anzahl der verfügbaren COR_IL_MAP Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="ebfbb-117">Wenn `cMap` nicht NULL ist, stellt es die Speicherkapazität des `map`-Arrays dar.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="ebfbb-118">Wenn die-Methode zurückgibt, `map` enthält maximal `cMap` Elemente und `pcMap` ist auf die Anzahl der COR_IL_MAP Werte festgelegt, die tatsächlich in das Array geschrieben wurden `map` .</span><span class="sxs-lookup"><span data-stu-id="ebfbb-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="ebfbb-119">Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="ebfbb-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebfbb-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ebfbb-120">Requirements</span></span>  

 <span data-ttu-id="ebfbb-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebfbb-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebfbb-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebfbb-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebfbb-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebfbb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebfbb-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebfbb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebfbb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebfbb-125">See also</span></span>

- [<span data-ttu-id="ebfbb-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="ebfbb-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="ebfbb-127">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebfbb-127">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="ebfbb-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfbb-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
