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
ms.openlocfilehash: d41ccd30707eba269bbac7231e06792363615544
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719319"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="33be4-102">ICorProfilerCallback::RemotingClientInvocationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="33be4-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>

<span data-ttu-id="33be4-103">Benachrichtigt den Profiler, dass ein Remotingaufrufe auf dem Client ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="33be4-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33be4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33be4-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="33be4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33be4-105">Remarks</span></span>  

 <span data-ttu-id="33be4-106">Wenn der remotingbefehl synchron war, kann er auch auf dem Server abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="33be4-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="33be4-107">Wenn der Remotingaufrufe asynchron war, wird möglicherweise dennoch eine Antwort erwartet, wenn der-Befehl verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="33be4-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="33be4-108">Wenn eine Antwort erwartet wird, wird Sie als ein Aufrufen von [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) und eines zusätzlichen Aufrufs von ausgelöst, `RemotingClientInvocationFinished` um die erforderliche sekundäre Verarbeitung eines asynchronen Aufrufs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="33be4-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="33be4-109">Jedes der folgenden paar Rückrufe findet im gleichen Thread statt:</span><span class="sxs-lookup"><span data-stu-id="33be4-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="33be4-110">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="33be4-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="33be4-111">[ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: remotingclientinvocationabgeschlossene](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="33be4-111">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="33be4-112">[ICorProfilerCallback:: remotingserverinvocationzurück gegeben](icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="33be4-112">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="33be4-113">Beachten Sie die folgenden Probleme bei den Remoting-Rückrufen:</span><span class="sxs-lookup"><span data-stu-id="33be4-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="33be4-114">Die Ausführung einer Remoting-Funktion wird von der Profiler-API nicht reflektiert, sodass Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="33be4-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="33be4-115">Der tatsächliche Aufruf erfolgt über ein Proxy Objekt. für den Profiler wird angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33be4-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="33be4-116">Der Profiler empfängt keine genauen Benachrichtigungen für asynchrone Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="33be4-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33be4-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="33be4-117">Requirements</span></span>  

 <span data-ttu-id="33be4-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33be4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33be4-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33be4-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33be4-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33be4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33be4-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33be4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33be4-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33be4-122">See also</span></span>

- [<span data-ttu-id="33be4-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33be4-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
