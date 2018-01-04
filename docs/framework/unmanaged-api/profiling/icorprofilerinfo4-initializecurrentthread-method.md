---
title: ICorProfilerInfo4::InitializeCurrentThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4::InitializeCurrentThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f3c261068b38861dca2633a490e46d9f44371d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="f53e0-102">ICorProfilerInfo4::InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="f53e0-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="f53e0-103">Initialisiert den aktuellen Thread im Vorfeld nachfolgende Profiler, die auf dem gleichen Thread-API-Aufrufe, sodass dieser Deadlock vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="f53e0-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f53e0-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f53e0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f53e0-105">Remarks</span></span>  
 <span data-ttu-id="f53e0-106">Es wird empfohlen, Sie rufen `InitializeCurrentThread` auf einen beliebigen Thread, der einen Profiler angerufen API sind Threads angehalten.</span><span class="sxs-lookup"><span data-stu-id="f53e0-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="f53e0-107">Diese Methode wird von Profilern, die ihre eigenen Thread aufrufen, erstellen in der Regel verwendet die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode zum Ausführen der Stapel durchläuft, während der Zielthread angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="f53e0-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="f53e0-108">Durch Aufrufen von `InitializeCurrentThread` Sobald bei der Profiler zuerst die Stichproben-Thread erstellt, können Profilern sicherstellen die pro Thread verzögerte Initialisierung, die die CLR beim ersten Aufruf andernfalls ausführen würden `DoStackSnapshot` kann nun erfolgen sicher Wenn keine anderen Threads sind angehalten.</span><span class="sxs-lookup"><span data-stu-id="f53e0-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f53e0-109">`InitializeCurrentThread`führt die Initialisierung im voraus, um Aufgaben abgeschlossen sind, die Sperren und kann zu einem deadlock.</span><span class="sxs-lookup"><span data-stu-id="f53e0-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="f53e0-110">Rufen Sie `InitializeCurrentThread` nur, wenn keine angehaltenen Threads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f53e0-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f53e0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f53e0-111">Requirements</span></span>  
 <span data-ttu-id="f53e0-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f53e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f53e0-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f53e0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f53e0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f53e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f53e0-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f53e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53e0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53e0-116">See Also</span></span>  
 [<span data-ttu-id="f53e0-117">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f53e0-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="f53e0-118">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f53e0-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f53e0-119">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f53e0-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
