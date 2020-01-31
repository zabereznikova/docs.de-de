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
ms.openlocfilehash: 8ae58344a7a17637bf08b9b5179abdba7e7060d6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866025"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="27b4c-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="27b4c-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="27b4c-103">Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="27b4c-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27b4c-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27b4c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="27b4c-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="27b4c-106">in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) unter den folgenden Bedingungen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="27b4c-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="27b4c-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="27b4c-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="27b4c-108">Der Kanal hat die Nachricht erfolgreich übertragen.</span><span class="sxs-lookup"><span data-stu-id="27b4c-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="27b4c-109">GUID-Cookies sind im serverseitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="27b4c-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="27b4c-110">Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.</span><span class="sxs-lookup"><span data-stu-id="27b4c-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="27b4c-111">in Ein-Wert, der `true` wird, wenn der-Befehl asynchron ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="27b4c-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b4c-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27b4c-112">Requirements</span></span>  
 <span data-ttu-id="27b4c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b4c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b4c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27b4c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27b4c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27b4c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27b4c-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b4c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b4c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27b4c-117">See also</span></span>

- [<span data-ttu-id="27b4c-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27b4c-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
