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
ms.openlocfilehash: 5947541204edf7fd4359dfa3aca78ea62c8009c6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="85f01-102">ICorProfilerCallback::RemotingServerReceivingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="85f01-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="85f01-103">Benachrichtigt den Profiler, dass der Prozess eine remote-Methode aufrufen oder die Aktivierung der Anforderung empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="85f01-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85f01-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85f01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85f01-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="85f01-106">[in] Ein Wert, der entsprechen, wird mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="85f01-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="85f01-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="85f01-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="85f01-108">Der Kanal kann erfolgreich sendet die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="85f01-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="85f01-109">GUID-Cookies werden auf der Clientseite Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="85f01-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="85f01-110">Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="85f01-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="85f01-111">[in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="85f01-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f01-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85f01-112">Remarks</span></span>  
 <span data-ttu-id="85f01-113">Wenn die nachrichtenanforderung asynchron ist, kann die Anforderung von jedem beliebigen Thread bedient werden.</span><span class="sxs-lookup"><span data-stu-id="85f01-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f01-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85f01-114">Requirements</span></span>  
 <span data-ttu-id="85f01-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f01-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f01-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85f01-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85f01-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85f01-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85f01-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f01-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f01-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85f01-119">See Also</span></span>  
 [<span data-ttu-id="85f01-120">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85f01-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
