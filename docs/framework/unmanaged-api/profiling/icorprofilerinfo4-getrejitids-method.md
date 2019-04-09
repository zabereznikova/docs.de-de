---
title: ICorProfilerInfo4::GetReJITIDs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121614"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="01243-102">ICorProfilerInfo4::GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="01243-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="01243-103">Gibt ein Array von IDs, die alle erneut JIT-kompilierte Versionen der angegebenen Funktion zu identifizieren, die immer noch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="01243-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="01243-104">Dies schließt erneut JIT-kompilierte Versionen der Funktionen, die anschließend zurückgesetzt, aber noch nicht verfügbar (z. B. wenn die Anwendungsdomäne mit der wiederhergestellten Funktion noch verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="01243-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01243-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="01243-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01243-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="01243-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="01243-107">[in] Die `FunctionID` Funktion-Instanz für die Versionen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="01243-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="01243-108">[in] Die Anzahl der erneut JIT-kompilierten IDs zugewiesen werden, der `reJitIds` Array.</span><span class="sxs-lookup"><span data-stu-id="01243-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="01243-109">[out] Die tatsächliche Anzahl der erneut JIT-kompilierten-IDs.</span><span class="sxs-lookup"><span data-stu-id="01243-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="01243-110">[out] Ein vom Aufrufer reservierte Array, die die erneut JIT-kompilierten-IDs für die angegebene Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="01243-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01243-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01243-111">Remarks</span></span>  
 `GetReJITIDs` <span data-ttu-id="01243-112">Listet die aktiven erneut JIT-kompilierten-IDs für eine Instanz für die angegebene Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="01243-112">enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="01243-113">Dabei wird das gleiche Verwendungsmuster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer reservierte Puffer zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="01243-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01243-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01243-114">Requirements</span></span>  
 <span data-ttu-id="01243-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01243-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01243-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01243-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01243-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01243-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="01243-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="01243-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="01243-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01243-119">See also</span></span>

- [<span data-ttu-id="01243-120">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01243-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="01243-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="01243-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="01243-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="01243-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
