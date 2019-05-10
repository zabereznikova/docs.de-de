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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bec96ef50416d946b1f12fd503e04f976ca58f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662930"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="7a4f0-102">ICorProfilerCallback::RemotingClientInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="7a4f0-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="7a4f0-103">Benachrichtigt den Profiler, dass ein Remoteaufrufs gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7a4f0-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a4f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a4f0-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7a4f0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a4f0-105">Remarks</span></span>  
 <span data-ttu-id="7a4f0-106">Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.</span><span class="sxs-lookup"><span data-stu-id="7a4f0-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="7a4f0-107">Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:</span><span class="sxs-lookup"><span data-stu-id="7a4f0-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="7a4f0-108">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="7a4f0-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="7a4f0-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="7a4f0-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="7a4f0-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="7a4f0-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="7a4f0-111">Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:</span><span class="sxs-lookup"><span data-stu-id="7a4f0-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="7a4f0-112">Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="7a4f0-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="7a4f0-113">Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a4f0-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="7a4f0-114">Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7a4f0-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a4f0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a4f0-115">Requirements</span></span>  
 <span data-ttu-id="7a4f0-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a4f0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a4f0-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a4f0-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a4f0-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a4f0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a4f0-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4f0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4f0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a4f0-120">See also</span></span>

- [<span data-ttu-id="7a4f0-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4f0-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
