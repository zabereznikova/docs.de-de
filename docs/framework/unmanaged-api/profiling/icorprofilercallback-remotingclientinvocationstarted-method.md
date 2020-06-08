---
title: ICorProfilerCallback::RemotingClientInvocationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
ms.openlocfilehash: 8a042e71690b5ae77c1e4cda7be394a163ab2774
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503262"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="60463-102">ICorProfilerCallback::RemotingClientInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="60463-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="60463-103">Benachrichtigt den Profiler, dass ein remotingbefehl gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="60463-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60463-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60463-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="60463-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="60463-105">Remarks</span></span>  
 <span data-ttu-id="60463-106">Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.</span><span class="sxs-lookup"><span data-stu-id="60463-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="60463-107">Jedes der folgenden paar Rückrufe findet im gleichen Thread statt:</span><span class="sxs-lookup"><span data-stu-id="60463-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="60463-108">`RemotingClientInvocationStarted`und [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="60463-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="60463-109">[ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: remotingclientinvocationabgeschlossene](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="60463-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="60463-110">[ICorProfilerCallback:: remotingserverinvocationzurück gegeben](icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="60463-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="60463-111">Beachten Sie die folgenden Probleme bei den Remoting-Rückrufen:</span><span class="sxs-lookup"><span data-stu-id="60463-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="60463-112">Die Ausführung einer Remoting-Funktion wird von der Profiler-API nicht reflektiert, sodass Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="60463-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="60463-113">Der tatsächliche Aufruf erfolgt über ein Proxy Objekt. für den Profiler wird angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60463-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="60463-114">Der Profiler empfängt keine genauen Benachrichtigungen für asynchrone Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="60463-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60463-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="60463-115">Requirements</span></span>  
 <span data-ttu-id="60463-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60463-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60463-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60463-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60463-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60463-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60463-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60463-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60463-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="60463-120">See also</span></span>

- [<span data-ttu-id="60463-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60463-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
