---
title: ICorDebugILCode2::GetInstrumentedILMap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b740f378b4fd15fe6bf4a9832348869878e2a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="25b0a-102">ICorDebugILCode2::GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="25b0a-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="25b0a-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="25b0a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="25b0a-104">Gibt eine Zuordnung von Profiler-instrumentierten Intermediate Language (IL) Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="25b0a-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b0a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25b0a-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25b0a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="25b0a-106">Parameters</span></span>  
 <span data-ttu-id="25b0a-107">cMap</span><span class="sxs-lookup"><span data-stu-id="25b0a-107">cMap</span></span>  
 <span data-ttu-id="25b0a-108">[in] Die Speicherkapazität für das `map`-Array.</span><span class="sxs-lookup"><span data-stu-id="25b0a-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="25b0a-109">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="25b0a-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="25b0a-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="25b0a-110">pcMap</span></span>  
 <span data-ttu-id="25b0a-111">[out] Die Anzahl der COR_IL_MAP-Werte, die in das Zuordnungsarray geschrieben.</span><span class="sxs-lookup"><span data-stu-id="25b0a-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="25b0a-112">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="25b0a-112">map</span></span>  
 <span data-ttu-id="25b0a-113">[out] Ein Array von COR_IL_MAP-Werte, die Informationen über Zuordnungen von Profiler-instrumentierter IL zur IL der ursprünglichen Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="25b0a-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25b0a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25b0a-114">Remarks</span></span>  
 <span data-ttu-id="25b0a-115">Wenn bei der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode, der Debugger kann diese Methode zum Abrufen der Zuordnung und die Zuordnung verwendet intern beim Berechnen des IL-für die Stack Offsets aufrufen ablaufverfolgungen und Variable Lebensdauer.</span><span class="sxs-lookup"><span data-stu-id="25b0a-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="25b0a-116">Wenn `cMap` ist 0 und `pcMap` nicht**null**, `pcMap` auf die Anzahl der verfügbaren COR_IL_MAP-Werte festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25b0a-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="25b0a-117">Wenn `cMap` nicht NULL ist, stellt es die Speicherkapazität des `map`-Arrays dar.</span><span class="sxs-lookup"><span data-stu-id="25b0a-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="25b0a-118">Wenn die Methode zurückkehrt, `map` höchstens `cMap` Elemente und `pcMap` festgelegt ist, um die Anzahl der tatsächlich geschriebenen COR_IL_MAP-Werte der `map` Array.</span><span class="sxs-lookup"><span data-stu-id="25b0a-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="25b0a-119">Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="25b0a-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25b0a-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25b0a-120">Requirements</span></span>  
 <span data-ttu-id="25b0a-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25b0a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b0a-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25b0a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25b0a-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25b0a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25b0a-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25b0a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b0a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25b0a-125">See Also</span></span>  
 [<span data-ttu-id="25b0a-126">ICorProfilerInfo:: SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="25b0a-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [<span data-ttu-id="25b0a-127">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25b0a-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="25b0a-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="25b0a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
