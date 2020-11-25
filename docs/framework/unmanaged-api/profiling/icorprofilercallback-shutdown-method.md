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
ms.openlocfilehash: 9761eb5085a77279c4d07d39946a5ad1453ecaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717241"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="51642-102">ICorProfilerCallback::Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="51642-102">ICorProfilerCallback::Shutdown Method</span></span>

<span data-ttu-id="51642-103">Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="51642-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51642-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51642-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="51642-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51642-105">Remarks</span></span>  

 <span data-ttu-id="51642-106">Der Profiler-Code kann Methoden der [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstelle nicht sicher aufrufen, nachdem die- `Shutdown` Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="51642-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="51642-107">Alle Aufrufe von `ICorProfilerInfo` Methoden führen zu einem nicht definierten Verhalten, nachdem die- `Shutdown` Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="51642-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="51642-108">Bestimmte unveränderliche Ereignisse können nach dem Herunterfahren weiterhin auftreten. der Profiler sollte darauf achten, dass Sie sofort zurückkehren, wenn dies auftritt.</span><span class="sxs-lookup"><span data-stu-id="51642-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="51642-109">Die- `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, für die die Profilerstellung ausgeführt wird, als verwalteter Code gestartet wird (d. h., der erste Frame im Prozess Stapel wird verwaltet).</span><span class="sxs-lookup"><span data-stu-id="51642-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="51642-110">Wenn die Anwendung als nicht verwalteter Code gestartet, aber später in verwalteten Code gesprungen ist, wird eine Instanz des Common Language Runtime (CLR) erstellt, dann `Shutdown` wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="51642-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="51642-111">In diesen Fällen sollte der Profiler in der Bibliothek eine Routine enthalten `DllMain` , die den DLL_PROCESS_DETACH-Wert verwendet, um Ressourcen freizugeben und eine Bereinigungs Verarbeitung der Daten durchzuführen, wie z. b. das Leeren von Ablauf Verfolgungen auf die Festplatte usw.</span><span class="sxs-lookup"><span data-stu-id="51642-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="51642-112">Im Allgemeinen muss der Profiler mit unerwarteten Herunterfahr Vorgängen zurechtkommen.</span><span class="sxs-lookup"><span data-stu-id="51642-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="51642-113">Beispielsweise kann ein Prozess durch die Win32's-Methode angehalten werden `TerminateProcess` (in Winbase. h deklariert).</span><span class="sxs-lookup"><span data-stu-id="51642-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="51642-114">In anderen Fällen hält die CLR bestimmte verwaltete Threads (Hintergrundthreads) an, ohne dass dafür ordnungsgemäße Zerstörungs Nachrichten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51642-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51642-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51642-115">Requirements</span></span>  

 <span data-ttu-id="51642-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51642-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51642-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51642-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51642-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51642-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51642-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51642-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51642-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51642-120">See also</span></span>

- [<span data-ttu-id="51642-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51642-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="51642-122">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="51642-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
