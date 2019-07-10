---
title: ICorProfilerCallback::RemotingServerSendingReply-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c73889a6daaa50d1694e786c78f50d0e87644967
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750429"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="0a8a9-102">ICorProfilerCallback::RemotingServerSendingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="0a8a9-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="0a8a9-103">Benachrichtigt den Profiler, dass der Prozess Verarbeitung eine Remotemethode aufrufen-Anforderung abgeschlossen hat und die Antwort über einen Kanal übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a8a9-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a8a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a8a9-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="0a8a9-106">[in] Ein Zeiger auf eine GUID, die mit dem Wert im bereitgestellten entspricht [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="0a8a9-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="0a8a9-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="0a8a9-108">Der Kanal ist erfolgreich, bei der Übermittlung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="0a8a9-109">GUID-Cookies sind bei der clientseitigen aktiv.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="0a8a9-110">Dies ermöglicht die einfache Kopplung der Remotingaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="0a8a9-111">[in] Ein Wert, `true` , wenn der Aufruf asynchron; andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0a8a9-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a8a9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a8a9-112">Requirements</span></span>  
 <span data-ttu-id="0a8a9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a8a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a8a9-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a8a9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a8a9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a8a9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a8a9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a8a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8a9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a8a9-117">See also</span></span>

- [<span data-ttu-id="0a8a9-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a8a9-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
