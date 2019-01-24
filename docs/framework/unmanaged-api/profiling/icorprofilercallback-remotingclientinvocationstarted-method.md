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
ms.openlocfilehash: c0cc27bd6a5c0cb85f4822a4481d9588705b71bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575959"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="82430-102">ICorProfilerCallback::RemotingClientInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="82430-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="82430-103">Benachrichtigt den Profiler, dass ein Remoteaufrufs gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="82430-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82430-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82430-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="82430-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82430-105">Remarks</span></span>  
 <span data-ttu-id="82430-106">Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.</span><span class="sxs-lookup"><span data-stu-id="82430-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="82430-107">Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:</span><span class="sxs-lookup"><span data-stu-id="82430-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="82430-108">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="82430-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="82430-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="82430-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="82430-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="82430-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="82430-111">Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:</span><span class="sxs-lookup"><span data-stu-id="82430-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="82430-112">Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="82430-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="82430-113">Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82430-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="82430-114">Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="82430-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82430-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82430-115">Requirements</span></span>  
 <span data-ttu-id="82430-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82430-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82430-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82430-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82430-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82430-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82430-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82430-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82430-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82430-120">See also</span></span>
- [<span data-ttu-id="82430-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82430-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
