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
ms.openlocfilehash: e25cbfabc10da0c7b1095a956583bb5c7450dba9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445810"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="0caa4-102">ICorProfilerCallback::RemotingClientReceivingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="0caa4-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="0caa4-103">Benachrichtigt den Profiler, dass der serverseitige Teil eines remotingaufrufes abgeschlossen wurde und der Client die Antwort nun empfängt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0caa4-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0caa4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0caa4-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0caa4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0caa4-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="0caa4-106">in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) unter den folgenden Bedingungen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="0caa4-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="0caa4-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="0caa4-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="0caa4-108">Der Kanal hat die Nachricht erfolgreich übertragen.</span><span class="sxs-lookup"><span data-stu-id="0caa4-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="0caa4-109">GUID-Cookies sind im serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="0caa4-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="0caa4-110">Dies ermöglicht eine einfache Kopplung von Remoting-aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0caa4-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="0caa4-111">in Ein-Wert, der `true` wird, wenn der-Befehl asynchron ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0caa4-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0caa4-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0caa4-112">Requirements</span></span>  
 <span data-ttu-id="0caa4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0caa4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0caa4-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0caa4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0caa4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0caa4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0caa4-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0caa4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0caa4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0caa4-117">See also</span></span>

- [<span data-ttu-id="0caa4-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0caa4-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
