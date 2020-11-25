---
title: ICorProfilerInfo4::InitializeCurrentThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: 51f16523c00cc3dd95b786f1586ccfd75ce8d5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733827"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="80858-102">ICorProfilerInfo4::InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="80858-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>

<span data-ttu-id="80858-103">Initialisiert den aktuellen Thread vor nachfolgenden Profiler-API-aufrufen im gleichen Thread, sodass der Deadlock vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="80858-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80858-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80858-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="80858-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80858-105">Remarks</span></span>  

 <span data-ttu-id="80858-106">`InitializeCurrentThread`Es wird empfohlen, für jeden Thread aufzurufen, der eine Profiler-API aufruft, während Angehaltene Threads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="80858-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="80858-107">Diese Methode wird in der Regel von samplingprofilergeräten verwendet, die ihren eigenen Thread erstellen, um die [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode aufzurufen, während der Zielthread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="80858-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="80858-108">Durch einen Aufruf von `InitializeCurrentThread` einmal, wenn der Profiler erstmalig den Samplingthread erstellt, können Profiler sicherstellen, dass die verzögerte Initialisierung pro Thread, die die CLR andernfalls während des ersten Aufrufs von ausführen würde, `DoStackSnapshot` nun sicher auftreten kann, wenn keine anderen Threads angehalten werden</span><span class="sxs-lookup"><span data-stu-id="80858-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80858-109">`InitializeCurrentThread` führt die Initialisierung im Voraus aus, um Aufgaben abzuschließen, die Sperren akzeptieren und möglicherweise einen Deadlock verursachen.</span><span class="sxs-lookup"><span data-stu-id="80858-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="80858-110">Wird nur aufgerufen, wenn keine angehaltenen `InitializeCurrentThread` Threads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="80858-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80858-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="80858-111">Requirements</span></span>  

 <span data-ttu-id="80858-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80858-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80858-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80858-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80858-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80858-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80858-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80858-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80858-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80858-116">See also</span></span>

- [<span data-ttu-id="80858-117">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80858-117">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="80858-118">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="80858-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="80858-119">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="80858-119">Profiling</span></span>](index.md)
