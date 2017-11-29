---
title: ICorProfilerCallback::RemotingClientSendingMessage-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a77acb736cec02da6839335e981016469eeb42b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="99b2c-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="99b2c-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="99b2c-103">Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="99b2c-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99b2c-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99b2c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99b2c-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="99b2c-106">[in] Ein Wert mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="99b2c-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="99b2c-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="99b2c-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="99b2c-108">Der Kanal kann erfolgreich sendet die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="99b2c-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="99b2c-109">GUID-Cookies werden auf den serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="99b2c-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="99b2c-110">Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="99b2c-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="99b2c-111">[in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="99b2c-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99b2c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99b2c-112">Requirements</span></span>  
 <span data-ttu-id="99b2c-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99b2c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b2c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99b2c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99b2c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99b2c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99b2c-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b2c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b2c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99b2c-117">See Also</span></span>  
 [<span data-ttu-id="99b2c-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99b2c-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
