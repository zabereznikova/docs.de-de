---
title: ICorProfilerCallback::RemotingServerSendingReply-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerSendingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b99b2de235634b715a6f5ba9fee9ee49ab34063a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="d2c22-102">ICorProfilerCallback::RemotingServerSendingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="d2c22-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="d2c22-103">Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remotemethode Aufruf-Anforderung abgeschlossen und die Antwort über einen Kanal übertragen wird hat.</span><span class="sxs-lookup"><span data-stu-id="d2c22-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2c22-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2c22-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2c22-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="d2c22-106">[in] Ein Zeiger auf eine GUID, die mit dem Wert im bereitgestellten entsprechen wird [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="d2c22-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="d2c22-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="d2c22-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="d2c22-108">Der Kanal kann erfolgreich sendet die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d2c22-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="d2c22-109">GUID-Cookies werden auf der Clientseite Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="d2c22-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="d2c22-110">Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="d2c22-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="d2c22-111">[in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d2c22-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c22-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2c22-112">Requirements</span></span>  
 <span data-ttu-id="d2c22-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2c22-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c22-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2c22-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2c22-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2c22-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2c22-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c22-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2c22-117">See Also</span></span>  
 [<span data-ttu-id="d2c22-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2c22-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
