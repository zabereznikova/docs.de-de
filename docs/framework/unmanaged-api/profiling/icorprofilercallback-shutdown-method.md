---
title: ICorProfilerCallback::Shutdown-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1696cb49170ba245a657e5efb6c8ba4b694af32f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192640"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="914ea-102">ICorProfilerCallback::Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="914ea-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="914ea-103">Benachrichtigt den Profiler an, dass die Anwendung heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="914ea-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="914ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="914ea-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="914ea-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="914ea-105">Remarks</span></span>  
 <span data-ttu-id="914ea-106">Der Profilercode kann nicht sicher Methoden zum Aufrufen der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle nach der `Shutdown` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="914ea-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="914ea-107">Alle Aufrufe von `ICorProfilerInfo` Methoden zu nicht definiertem Verhalten nach der `Shutdown` Methodenrückgabe.</span><span class="sxs-lookup"><span data-stu-id="914ea-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="914ea-108">Bestimmte unveränderliche Ereignisse können weiterhin nach dem Herunterfahren auftreten. der Profiler sollte sorgfältig und zurückgeben, sofort, wenn dies der Fall.</span><span class="sxs-lookup"><span data-stu-id="914ea-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="914ea-109">Die `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, die ein Profil erstellt wird als verwalteter Code gestartet wurde (d. h. der erste Frame im Stapel Prozess verwaltet wird).</span><span class="sxs-lookup"><span data-stu-id="914ea-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="914ea-110">Wenn die Anwendung gestartet wird, als nicht verwalteter Code, aber später erfolgte ein in verwaltetem Code Sprung, wodurch eine Instanz von die common Language Runtime (CLR), klicken Sie dann `Shutdown` wird nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="914ea-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="914ea-111">In diesen Fällen sollte der Profiler in der Bibliothek enthalten eine `DllMain` Routine, die das DLL_PROZESS_DETACH verwendet Wert, um alle Ressourcen freizugeben und verarbeiten Sie die Bereinigung seiner Daten, z.B. das Leeren der ablaufverfolgungen auf dem Datenträger und so weiter.</span><span class="sxs-lookup"><span data-stu-id="914ea-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="914ea-112">Im Allgemeinen muss der Profiler mit unerwartetem Herunterfahren umgehen können.</span><span class="sxs-lookup"><span data-stu-id="914ea-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="914ea-113">Beispielsweise kann ein Prozess angehalten werden, von einer Win32 `TerminateProcess` Methode (deklariert in Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="914ea-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="914ea-114">In anderen Fällen wird die CLR bestimmte verwaltete Threads (Hintergrundthreads) angehalten, ohne die ordnungsgemäße Zerstörung Nachrichten für diese Bereitstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="914ea-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="914ea-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="914ea-115">Requirements</span></span>  
 <span data-ttu-id="914ea-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="914ea-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="914ea-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="914ea-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="914ea-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="914ea-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="914ea-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="914ea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="914ea-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="914ea-120">See also</span></span>

- [<span data-ttu-id="914ea-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="914ea-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="914ea-122">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="914ea-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
