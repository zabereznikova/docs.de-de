---
title: ICorProfilerCallback::RemotingClientReceivingReply-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f1dd027dc113abfceeb88abbc82c69ed395584e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="491e3-102">ICorProfilerCallback::RemotingClientReceivingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="491e3-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="491e3-103">Benachrichtigt den Profiler, die der serverseitigen Teil eines Remotingaufrufs abgeschlossen ist und der Client ist jetzt empfängt und verarbeitet die Antwort.</span><span class="sxs-lookup"><span data-stu-id="491e3-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="491e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="491e3-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="491e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="491e3-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="491e3-106">[in] Ein Wert, der entsprechen, wird mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="491e3-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="491e3-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="491e3-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="491e3-108">Der Kanal kann erfolgreich sendet die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="491e3-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="491e3-109">GUID-Cookies werden auf den serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="491e3-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="491e3-110">Dies ermöglicht einfache Kopplung Remoteaufrufe.</span><span class="sxs-lookup"><span data-stu-id="491e3-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="491e3-111">[in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="491e3-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="491e3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="491e3-112">Requirements</span></span>  
 <span data-ttu-id="491e3-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="491e3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="491e3-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="491e3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="491e3-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="491e3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="491e3-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="491e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491e3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="491e3-117">See Also</span></span>  
 [<span data-ttu-id="491e3-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="491e3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
