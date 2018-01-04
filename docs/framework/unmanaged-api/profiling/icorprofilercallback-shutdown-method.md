---
title: ICorProfilerCallback::Shutdown-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42c9abc3c255f7ddda5e7934c495b073a7b1f6fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="65a75-102">ICorProfilerCallback::Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="65a75-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="65a75-103">Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="65a75-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65a75-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="65a75-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65a75-105">Remarks</span></span>  
 <span data-ttu-id="65a75-106">Der Profilercode kann nicht sicher Aufrufen von Methoden der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle nach der `Shutdown` -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="65a75-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="65a75-107">Alle Aufrufe von `ICorProfilerInfo` Methoden zu nicht definiertem Verhalten nach der `Shutdown` -Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="65a75-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="65a75-108">Bestimmte unveränderliche Ereignisse können nach dem Herunterfahren weiterhin auftreten. der Profiler sollte zurückgeben, sofort, wenn in diesem Fall kümmern.</span><span class="sxs-lookup"><span data-stu-id="65a75-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="65a75-109">Die `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, die ein Profil erstellt wird als verwalteter Code gestartet (d. h. der erste Frame auf dem Stapel Prozess verwaltet wird).</span><span class="sxs-lookup"><span data-stu-id="65a75-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="65a75-110">Wenn die Anwendung als nicht verwalteter Code gestartet, jedoch später erfolgte ein in verwaltetem Code Sprung, wodurch eine Instanz von der common Language Runtime (CLR), klicken Sie dann `Shutdown` wird nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="65a75-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="65a75-111">In diesen Fällen sollte der Profiler in der Bibliothek enthalten eine `DllMain` Routine, die die DLL_PROCESS_DETACH verwendet der Wert, der alle Ressourcen frei und führt eine Bereinigung Verarbeitung seiner Daten wie z. B. das leeren von ablaufverfolgungen und so weiter auf den Datenträger.</span><span class="sxs-lookup"><span data-stu-id="65a75-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="65a75-112">Im Allgemeinen muss der Profiler mit unerwartetem Herunterfahren bewältigen.</span><span class="sxs-lookup"><span data-stu-id="65a75-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="65a75-113">Beispielsweise kann ein Prozess von einer Win32 angehalten `TerminateProcess` (deklariert in Winbase.h) Methode.</span><span class="sxs-lookup"><span data-stu-id="65a75-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="65a75-114">In anderen Fällen wird die CLR bestimmte verwaltete Threads (Hintergrundthreads) angehalten, ohne ordnungsgemäßes Zerstörung Nachrichten für diese Bereitstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="65a75-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a75-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65a75-115">Requirements</span></span>  
 <span data-ttu-id="65a75-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a75-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a75-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65a75-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65a75-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a75-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a75-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a75-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a75-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65a75-120">See Also</span></span>  
 [<span data-ttu-id="65a75-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65a75-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="65a75-122">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="65a75-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
