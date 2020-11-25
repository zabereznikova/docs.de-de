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
ms.openlocfilehash: 22b9970556dd9d8b5070f38a7712462aa5a4aae2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720164"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="f4b21-102">ICorProfilerCallback::RemotingClientInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="f4b21-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>

<span data-ttu-id="f4b21-103">Benachrichtigt den Profiler, dass ein remotingbefehl gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4b21-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4b21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4b21-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f4b21-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4b21-105">Remarks</span></span>  

 <span data-ttu-id="f4b21-106">Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.</span><span class="sxs-lookup"><span data-stu-id="f4b21-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="f4b21-107">Jedes der folgenden paar Rückrufe findet im gleichen Thread statt:</span><span class="sxs-lookup"><span data-stu-id="f4b21-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="f4b21-108">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="f4b21-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="f4b21-109">[ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: remotingclientinvocationabgeschlossene](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="f4b21-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="f4b21-110">[ICorProfilerCallback:: remotingserverinvocationzurück gegeben](icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="f4b21-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="f4b21-111">Beachten Sie die folgenden Probleme bei den Remoting-Rückrufen:</span><span class="sxs-lookup"><span data-stu-id="f4b21-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="f4b21-112">Die Ausführung einer Remoting-Funktion wird von der Profiler-API nicht reflektiert, sodass Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="f4b21-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="f4b21-113">Der tatsächliche Aufruf erfolgt über ein Proxy Objekt. für den Profiler wird angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4b21-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="f4b21-114">Der Profiler empfängt keine genauen Benachrichtigungen für asynchrone Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f4b21-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4b21-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f4b21-115">Requirements</span></span>  

 <span data-ttu-id="f4b21-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4b21-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b21-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4b21-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4b21-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4b21-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4b21-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b21-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b21-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4b21-120">See also</span></span>

- [<span data-ttu-id="f4b21-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4b21-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
