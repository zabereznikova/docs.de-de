---
title: ICorProfilerCallback::RemotingServerReceivingMessage-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerReceivingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4542f5362d83bc5c0419b9f1ff389c9a21aad29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="f9bd2-102">ICorProfilerCallback::RemotingServerReceivingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="f9bd2-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="f9bd2-103">Benachrichtigt den Profiler, dass der Prozess eine remote-Methode aufrufen oder die Aktivierung der Anforderung empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9bd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9bd2-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9bd2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9bd2-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="f9bd2-106">[in] Ein Wert, der entsprechen, wird mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="f9bd2-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="f9bd2-108">Der Kanal kann erfolgreich sendet die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="f9bd2-109">GUID-Cookies werden auf der Clientseite Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="f9bd2-110">Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="f9bd2-111">[in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9bd2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9bd2-112">Remarks</span></span>  
 <span data-ttu-id="f9bd2-113">Wenn die nachrichtenanforderung asynchron ist, kann die Anforderung von jedem beliebigen Thread bedient werden.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9bd2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9bd2-114">Requirements</span></span>  
 <span data-ttu-id="f9bd2-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9bd2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9bd2-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9bd2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9bd2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9bd2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9bd2-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9bd2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bd2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9bd2-119">See Also</span></span>  
 [<span data-ttu-id="f9bd2-120">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9bd2-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
