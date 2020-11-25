---
title: ICorProfilerCallback3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: fd482bfe8e95a53cafd1530c88f09df146a1b150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729433"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="4f38e-102">ICorProfilerCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f38e-102">ICorProfilerCallback3 Interface</span></span>

<span data-ttu-id="4f38e-103">Stellt Rückruf Methoden bereit, die von der Common Language Runtime (CLR) zum Kommunizieren von Anfüge-und Trenn Zustandsinformationen an den Profiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f38e-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f38e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f38e-104">Methods</span></span>  
  
|<span data-ttu-id="4f38e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4f38e-105">Method</span></span>|<span data-ttu-id="4f38e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4f38e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f38e-107">InitializeForAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="4f38e-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="4f38e-108">Wird von der CLR aufgerufen, um dem Profiler die Möglichkeit zu geben, seinen Zustand nach einem Anfüge Vorgang zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4f38e-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="4f38e-109">ProfilerAttachComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="4f38e-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="4f38e-110">Wird von der CLR aufgerufen, um anzugeben, dass der Profiler jetzt die Catch-Methode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="4f38e-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="4f38e-111">ProfilerDetachSucceeded-Methode</span><span class="sxs-lookup"><span data-stu-id="4f38e-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="4f38e-112">Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.</span><span class="sxs-lookup"><span data-stu-id="4f38e-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f38e-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4f38e-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f38e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4f38e-114">Requirements</span></span>  

 <span data-ttu-id="4f38e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f38e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f38e-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f38e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f38e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f38e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f38e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f38e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f38e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f38e-119">See also</span></span>

- [<span data-ttu-id="4f38e-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f38e-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4f38e-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f38e-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="4f38e-122">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f38e-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="4f38e-123">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f38e-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
