---
title: ICorProfilerCallback::RemotingClientInvocationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77f86d12d3a19f1b02ece35c8b717e78802f74f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="04252-102">ICorProfilerCallback::RemotingClientInvocationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="04252-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="04252-103">Benachrichtigt den Profiler, dass ein Remotingaufruf auf dem Client bis zum Abschluss ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="04252-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04252-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04252-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="04252-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04252-105">Remarks</span></span>  
 <span data-ttu-id="04252-106">War der Remotingaufruf synchron, hat es auch auf dem Server bis zum Abschluss ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="04252-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="04252-107">War der Remoteaufruf asynchrone, möglicherweise eine Antwort noch erwartet werden, wenn der Aufruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="04252-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="04252-108">Wenn eine Antwort erwartet wird, wird er als Aufruf auftreten [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und ein zusätzlicher Aufruf `RemotingClientInvocationFinished` an, dass die erforderliche zweite Verarbeitung eines asynchronen Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="04252-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="04252-109">Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread auftreten:</span><span class="sxs-lookup"><span data-stu-id="04252-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="04252-110">`RemotingClientInvocationStarted`und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="04252-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="04252-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="04252-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="04252-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="04252-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="04252-113">Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:</span><span class="sxs-lookup"><span data-stu-id="04252-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="04252-114">Ausführung einer Remotingfunktion wird vom Profiler-API nicht widergespiegelt, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="04252-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="04252-115">Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; der Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04252-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="04252-116">Der Profiler empfängt keine genaue Benachrichtigungen für asynchrone Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="04252-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04252-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04252-117">Requirements</span></span>  
 <span data-ttu-id="04252-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04252-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04252-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04252-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04252-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04252-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04252-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04252-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04252-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04252-122">See Also</span></span>  
 [<span data-ttu-id="04252-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04252-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
