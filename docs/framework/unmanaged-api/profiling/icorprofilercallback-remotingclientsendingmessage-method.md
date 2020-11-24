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
ms.openlocfilehash: 2ef8f066831df1437bd0b6a6f155dd459cae1eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676841"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="da581-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="da581-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>

<span data-ttu-id="da581-103">Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="da581-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da581-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da581-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da581-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da581-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="da581-106">in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) unter den folgenden Bedingungen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="da581-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="da581-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="da581-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="da581-108">Der Kanal hat die Nachricht erfolgreich übertragen.</span><span class="sxs-lookup"><span data-stu-id="da581-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="da581-109">GUID-Cookies sind im serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="da581-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="da581-110">Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.</span><span class="sxs-lookup"><span data-stu-id="da581-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="da581-111">in Ein-Wert, `true` der ist, wenn der-Aufrufwert asynchron ist, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="da581-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da581-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="da581-112">Requirements</span></span>  

 <span data-ttu-id="da581-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da581-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da581-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da581-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da581-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da581-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da581-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da581-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da581-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da581-117">See also</span></span>

- [<span data-ttu-id="da581-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da581-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
