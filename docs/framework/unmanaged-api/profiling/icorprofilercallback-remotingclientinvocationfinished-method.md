---
title: ICorProfilerCallback::RemotingClientInvocationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8c29393f3127ec02d343221f28152fffbadb2b7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782946"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="42e3d-102">ICorProfilerCallback::RemotingClientInvocationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="42e3d-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="42e3d-103">Benachrichtigt den Profiler an, dass ein Remoteaufrufs bis zum Abschluss, auf dem Client ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="42e3d-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42e3d-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="42e3d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42e3d-105">Remarks</span></span>  
 <span data-ttu-id="42e3d-106">Wenn der Remotingaufruf für synchrone war, hat es auch auf dem Server bis zum Abschluss ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42e3d-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="42e3d-107">Wenn der Remotingaufruf für asynchrone war, ggf. eine Antwort immer noch erwartet werden, wenn der Aufruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="42e3d-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="42e3d-108">Wenn eine Antwort erwartet wird, wird er als Aufruf auftreten [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und einen zusätzlichen Aufruf `RemotingClientInvocationFinished` an die sekundären erforderliche Verarbeitung eines asynchronen Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="42e3d-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="42e3d-109">Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:</span><span class="sxs-lookup"><span data-stu-id="42e3d-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="42e3d-110">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="42e3d-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="42e3d-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="42e3d-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="42e3d-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="42e3d-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="42e3d-113">Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:</span><span class="sxs-lookup"><span data-stu-id="42e3d-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="42e3d-114">Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="42e3d-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="42e3d-115">Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42e3d-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="42e3d-116">Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="42e3d-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e3d-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42e3d-117">Requirements</span></span>  
 <span data-ttu-id="42e3d-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e3d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e3d-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42e3d-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42e3d-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42e3d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42e3d-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e3d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e3d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42e3d-122">See also</span></span>

- [<span data-ttu-id="42e3d-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42e3d-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
