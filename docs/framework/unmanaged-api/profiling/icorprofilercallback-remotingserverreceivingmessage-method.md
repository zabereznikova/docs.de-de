---
title: ICorProfilerCallback::RemotingServerReceivingMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67ec3bf10638538b49f1ec44ff583bdf4ba4ef9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572252"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="40e85-102">ICorProfilerCallback::RemotingServerReceivingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="40e85-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="40e85-103">Benachrichtigt den Profiler, dass der Prozess eine Remotemethode aufrufen oder die Aktivierung der Anforderung erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="40e85-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e85-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e85-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40e85-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="40e85-106">[in] Ein Wert, der entspricht, mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="40e85-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="40e85-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="40e85-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="40e85-108">Der Kanal ist erfolgreich, bei der Übermittlung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="40e85-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="40e85-109">GUID-Cookies sind bei der clientseitigen aktiv.</span><span class="sxs-lookup"><span data-stu-id="40e85-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="40e85-110">Dies ermöglicht die einfache Kopplung der Remotingaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="40e85-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="40e85-111">[in] Ein Wert, `true` , wenn der Aufruf asynchron; andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="40e85-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e85-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40e85-112">Remarks</span></span>  
 <span data-ttu-id="40e85-113">Wenn die nachrichtenanforderung asynchron ist, kann die Anforderung von einem beliebigen Thread bedient werden.</span><span class="sxs-lookup"><span data-stu-id="40e85-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e85-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e85-114">Requirements</span></span>  
 <span data-ttu-id="40e85-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40e85-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e85-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40e85-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40e85-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40e85-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40e85-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e85-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e85-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e85-119">See also</span></span>
- [<span data-ttu-id="40e85-120">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e85-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
