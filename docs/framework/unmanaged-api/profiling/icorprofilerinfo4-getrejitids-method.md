---
title: ICorProfilerInfo4::GetReJITIDs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetReJITIDs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="8104e-102">ICorProfilerInfo4::GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="8104e-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="8104e-103">Gibt ein Array von IDs, die alle JIT-kompilierten Version der angegebenen Funktion zu identifizieren, die dennoch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8104e-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="8104e-104">Dies schließt die JIT-kompilierten Versionen der Funktionen, die anschließend wiederhergestellt, jedoch noch nicht verfügbar (z. B. wenn die Anwendungsdomäne mit der wiederhergestellten Funktion weiterhin verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="8104e-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8104e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8104e-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8104e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8104e-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8104e-107">[in] Die `FunctionID` Funktion-Instanz für die Versionen aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="8104e-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="8104e-108">[in] Die Anzahl der JIT-kompilierten IDs zugeordnet, die der `reJitIds` Array.</span><span class="sxs-lookup"><span data-stu-id="8104e-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="8104e-109">[out] Die tatsächliche Anzahl der JIT-kompilierten-IDs.</span><span class="sxs-lookup"><span data-stu-id="8104e-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="8104e-110">[out] Ein vom Aufrufer zugewiesene Array, die der JIT-kompilierten-IDs für die angegebene Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="8104e-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8104e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8104e-111">Remarks</span></span>  
 <span data-ttu-id="8104e-112">`GetReJITIDs`Listet die aktiven JIT-kompilierten-IDs für eine Instanz für die angegebene Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="8104e-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="8104e-113">Es folgt demselben Nutzungsmuster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer reservierte Puffer zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="8104e-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8104e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8104e-114">Requirements</span></span>  
 <span data-ttu-id="8104e-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8104e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8104e-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8104e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8104e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8104e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8104e-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8104e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8104e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8104e-119">See Also</span></span>  
 [<span data-ttu-id="8104e-120">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8104e-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="8104e-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8104e-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8104e-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="8104e-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
