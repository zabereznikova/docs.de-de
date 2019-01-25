---
title: ICorProfilerCallback::RemotingClientSendingMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424e0323c018367560d4cf3542e9e8668575a03f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675191"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="bb336-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="bb336-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="bb336-103">Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="bb336-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb336-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb336-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb336-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb336-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="bb336-106">[in] Ein Wert, mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="bb336-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="bb336-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="bb336-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="bb336-108">Der Kanal ist erfolgreich, bei der Übermittlung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="bb336-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="bb336-109">GUID-Cookies werden auf den serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="bb336-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="bb336-110">Dies ermöglicht die einfache Kopplung der Remotingaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="bb336-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="bb336-111">[in] Ein Wert, `true` , wenn der Aufruf asynchron; andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="bb336-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb336-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb336-112">Requirements</span></span>  
 <span data-ttu-id="bb336-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb336-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb336-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb336-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb336-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb336-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb336-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb336-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb336-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb336-117">See also</span></span>
- [<span data-ttu-id="bb336-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb336-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
