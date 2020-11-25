---
title: ICorProfilerCallback::RemotingClientReceivingReply-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: 058c66af85da6c902e3d628e1b1479bb88c4fa85
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704850"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="c5b46-102">ICorProfilerCallback::RemotingClientReceivingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="c5b46-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>

<span data-ttu-id="c5b46-103">Benachrichtigt den Profiler, dass der serverseitige Teil eines remotingaufrufes abgeschlossen wurde und der Client die Antwort nun empfängt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c5b46-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5b46-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5b46-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="c5b46-106">in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) unter den folgenden Bedingungen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="c5b46-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="c5b46-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="c5b46-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="c5b46-108">Der Kanal hat die Nachricht erfolgreich übertragen.</span><span class="sxs-lookup"><span data-stu-id="c5b46-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="c5b46-109">GUID-Cookies sind im serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="c5b46-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="c5b46-110">Dies ermöglicht eine einfache Kopplung von Remoting-aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5b46-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="c5b46-111">in Ein-Wert, `true` der ist, wenn der-Aufrufwert asynchron ist, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="c5b46-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b46-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c5b46-112">Requirements</span></span>  

 <span data-ttu-id="c5b46-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5b46-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b46-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5b46-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5b46-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5b46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5b46-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b46-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5b46-117">See also</span></span>

- [<span data-ttu-id="c5b46-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5b46-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
