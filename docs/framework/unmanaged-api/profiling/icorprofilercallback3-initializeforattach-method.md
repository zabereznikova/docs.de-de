---
title: ICorProfilerCallback3::InitializeForAttach-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.InitializeForAttach Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 323f163774407ff2ddfd261ff6d6584a07ed7d8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="c360d-102">ICorProfilerCallback3::InitializeForAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="c360d-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="c360d-103">Wird von der CLS (Common Language Runtime) aufgerufen, um dem Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c360d-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c360d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c360d-104">Syntax</span></span>  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c360d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c360d-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="c360d-106">[in] Ein Schnittstellenzeiger für die `ICorProfilerInfo*`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c360d-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="c360d-107">[in] Ein Zeiger auf die Daten zu übergeben, um die [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode in seiner `pvClientData` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c360d-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="c360d-108">Wenn dieser Parameter NULL ist, ist `cbClientData` 0 (NULL).</span><span class="sxs-lookup"><span data-stu-id="c360d-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="c360d-109">Die CLR gibt diesen Arbeitsspeicher nach der Rückkehr von `InitializeForAttach` frei.</span><span class="sxs-lookup"><span data-stu-id="c360d-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="c360d-110">[in] Die Größe der Daten in Bytes, auf die `pvClientData` verweist.</span><span class="sxs-lookup"><span data-stu-id="c360d-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c360d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c360d-111">Remarks</span></span>  
 <span data-ttu-id="c360d-112">Die CLR ruft `InitializeForAttach` auf, um dem Profiler das Anfordern von Rückrufen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c360d-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c360d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c360d-113">Requirements</span></span>  
 <span data-ttu-id="c360d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c360d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c360d-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c360d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c360d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c360d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c360d-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c360d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c360d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c360d-118">See Also</span></span>  
 [<span data-ttu-id="c360d-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c360d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c360d-120">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c360d-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="c360d-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c360d-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c360d-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c360d-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
