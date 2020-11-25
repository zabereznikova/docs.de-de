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
ms.openlocfilehash: c85bba9a5d913820b69cbc214275b733a53197ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729446"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="4a358-102">ICorProfilerCallback3::InitializeForAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="4a358-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>

<span data-ttu-id="4a358-103">Wird von der CLS (Common Language Runtime) aufgerufen, um dem Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4a358-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a358-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a358-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a358-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a358-105">Parameters</span></span>  

 `pCorProfilerInfoUnk`  
 <span data-ttu-id="4a358-106">[in] Ein Schnittstellenzeiger für die `ICorProfilerInfo*`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4a358-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="4a358-107">in Ein Zeiger auf die Daten, die an die [iclrprofiling:: attachprofiler](iclrprofiling-attachprofiler-method.md) -Methode in Ihrem-Parameter übergeben werden `pvClientData` .</span><span class="sxs-lookup"><span data-stu-id="4a358-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="4a358-108">Wenn dieser Parameter NULL ist, ist `cbClientData` 0 (NULL).</span><span class="sxs-lookup"><span data-stu-id="4a358-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="4a358-109">Die CLR gibt diesen Arbeitsspeicher nach der Rückkehr von `InitializeForAttach` frei.</span><span class="sxs-lookup"><span data-stu-id="4a358-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="4a358-110">[in] Die Größe der Daten in Bytes, auf die `pvClientData` verweist.</span><span class="sxs-lookup"><span data-stu-id="4a358-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a358-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a358-111">Remarks</span></span>  

 <span data-ttu-id="4a358-112">Die CLR ruft `InitializeForAttach` auf, um dem Profiler das Anfordern von Rückrufen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4a358-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a358-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a358-113">Requirements</span></span>  

 <span data-ttu-id="4a358-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a358-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a358-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a358-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a358-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a358-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a358-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a358-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a358-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a358-118">See also</span></span>

- [<span data-ttu-id="4a358-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a358-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4a358-120">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a358-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4a358-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4a358-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4a358-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="4a358-122">Profiling</span></span>](index.md)
