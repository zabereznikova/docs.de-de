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
ms.openlocfilehash: 4729a8d3ac2c6f7ec51a032a07ebfd1c2838cb9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782907"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="78320-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="78320-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="78320-103">Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="78320-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78320-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78320-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78320-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78320-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="78320-106">[in] Ein Wert, mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) unter diesen Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="78320-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="78320-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="78320-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="78320-108">Der Kanal ist erfolgreich, bei der Übermittlung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="78320-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="78320-109">GUID-Cookies werden auf den serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="78320-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="78320-110">Dies ermöglicht die einfache Kopplung der Remotingaufrufe und die Erstellung einer logischen Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="78320-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="78320-111">[in] Ein Wert, `true` , wenn der Aufruf asynchron; andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="78320-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78320-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78320-112">Requirements</span></span>  
 <span data-ttu-id="78320-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78320-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78320-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78320-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78320-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78320-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78320-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78320-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78320-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78320-117">See also</span></span>

- [<span data-ttu-id="78320-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78320-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
