---
title: ICorProfilerCallback3::InitializeForAttach-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: 047516574595f9ffcd61360f51823da73a2f9733
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439516"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="5e0e7-102">ICorProfilerCallback3::InitializeForAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="5e0e7-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="5e0e7-103">Wird von der CLS (Common Language Runtime) aufgerufen, um dem Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e0e7-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e0e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e0e7-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="5e0e7-106">[in] Ein Schnittstellenzeiger für die `ICorProfilerInfo*`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="5e0e7-107">in Ein Zeiger auf die Daten, die an die [iclrprofiling:: attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) -Methode in Ihrem `pvClientData`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="5e0e7-108">Wenn dieser Parameter NULL ist, ist `cbClientData` 0 (NULL).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="5e0e7-109">Die CLR gibt diesen Arbeitsspeicher nach der Rückkehr von `InitializeForAttach` frei.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="5e0e7-110">[in] Die Größe der Daten in Bytes, auf die `pvClientData` verweist.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e0e7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e0e7-111">Remarks</span></span>  
 <span data-ttu-id="5e0e7-112">Die CLR ruft `InitializeForAttach` auf, um dem Profiler das Anfordern von Rückrufen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e0e7-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5e0e7-113">Requirements</span></span>  
 <span data-ttu-id="5e0e7-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e0e7-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e0e7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e0e7-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e0e7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e0e7-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e0e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0e7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e0e7-118">See also</span></span>

- [<span data-ttu-id="5e0e7-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e0e7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5e0e7-120">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e0e7-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5e0e7-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e0e7-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5e0e7-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="5e0e7-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
