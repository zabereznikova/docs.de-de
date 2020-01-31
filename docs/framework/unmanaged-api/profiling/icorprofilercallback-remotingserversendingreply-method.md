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
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865973"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="07b4d-102">ICorProfilerCallback::RemotingServerSendingReply-Methode</span><span class="sxs-lookup"><span data-stu-id="07b4d-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="07b4d-103">Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remote Methodenaufruf Anforderung abgeschlossen hat und die Antwort über einen Kanal überträgt.</span><span class="sxs-lookup"><span data-stu-id="07b4d-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07b4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07b4d-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07b4d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="07b4d-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="07b4d-106">in Ein Zeiger auf eine GUID, die dem Wert entspricht, der in [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) unter diesen Bedingungen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="07b4d-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="07b4d-107">Remoting-GUID-Cookies sind aktiv.</span><span class="sxs-lookup"><span data-stu-id="07b4d-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="07b4d-108">Der Kanal hat die Nachricht erfolgreich übertragen.</span><span class="sxs-lookup"><span data-stu-id="07b4d-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="07b4d-109">GUID-Cookies sind im Client seitigen Prozess aktiv.</span><span class="sxs-lookup"><span data-stu-id="07b4d-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="07b4d-110">Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.</span><span class="sxs-lookup"><span data-stu-id="07b4d-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="07b4d-111">in Ein-Wert, der `true` wird, wenn der-Befehl asynchron ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="07b4d-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07b4d-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07b4d-112">Requirements</span></span>  
 <span data-ttu-id="07b4d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07b4d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07b4d-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07b4d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07b4d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07b4d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07b4d-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b4d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b4d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07b4d-117">See also</span></span>

- [<span data-ttu-id="07b4d-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07b4d-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
