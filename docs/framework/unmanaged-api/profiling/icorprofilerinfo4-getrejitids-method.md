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
ms.openlocfilehash: cc16cd932fc2ce0cf5cb53c227081501e79ed2d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="7b93a-102">ICorProfilerInfo4::GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="7b93a-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="7b93a-103">Gibt ein Array von IDs, die alle JIT-kompilierten Version der angegebenen Funktion zu identifizieren, die dennoch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7b93a-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="7b93a-104">Dies schließt die JIT-kompilierten Versionen der Funktionen, die anschließend wiederhergestellt, jedoch noch nicht verfügbar (z. B. wenn die Anwendungsdomäne mit der wiederhergestellten Funktion weiterhin verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="7b93a-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b93a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b93a-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b93a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b93a-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7b93a-107">[in] Die `FunctionID` Funktion-Instanz für die Versionen aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="7b93a-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="7b93a-108">[in] Die Anzahl der JIT-kompilierten IDs zugeordnet, die der `reJitIds` Array.</span><span class="sxs-lookup"><span data-stu-id="7b93a-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="7b93a-109">[out] Die tatsächliche Anzahl der JIT-kompilierten-IDs.</span><span class="sxs-lookup"><span data-stu-id="7b93a-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="7b93a-110">[out] Ein vom Aufrufer zugewiesene Array, die der JIT-kompilierten-IDs für die angegebene Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="7b93a-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b93a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b93a-111">Remarks</span></span>  
 <span data-ttu-id="7b93a-112">`GetReJITIDs`Listet die aktiven JIT-kompilierten-IDs für eine Instanz für die angegebene Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="7b93a-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="7b93a-113">Es folgt demselben Nutzungsmuster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer reservierte Puffer zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="7b93a-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b93a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b93a-114">Requirements</span></span>  
 <span data-ttu-id="7b93a-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b93a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b93a-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b93a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b93a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b93a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b93a-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b93a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b93a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b93a-119">See Also</span></span>  
 [<span data-ttu-id="7b93a-120">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b93a-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="7b93a-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7b93a-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="7b93a-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="7b93a-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
