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
ms.openlocfilehash: ae9cb089ad6c0b0422063d3db413b97eb6ff1405
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445800"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="18af7-102">ICorProfilerCallback::RemotingClientSendingMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="18af7-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="18af7-103">Notifies the profiler that the client is sending a request to the server.</span><span class="sxs-lookup"><span data-stu-id="18af7-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18af7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18af7-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18af7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="18af7-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="18af7-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span><span class="sxs-lookup"><span data-stu-id="18af7-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="18af7-107">Remoting GUID cookies are active.</span><span class="sxs-lookup"><span data-stu-id="18af7-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="18af7-108">The channel succeeds in transmitting the message.</span><span class="sxs-lookup"><span data-stu-id="18af7-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="18af7-109">GUID cookies are active on the server-side process.</span><span class="sxs-lookup"><span data-stu-id="18af7-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="18af7-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span><span class="sxs-lookup"><span data-stu-id="18af7-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="18af7-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="18af7-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18af7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18af7-112">Requirements</span></span>  
 <span data-ttu-id="18af7-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18af7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18af7-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18af7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18af7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18af7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18af7-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18af7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18af7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18af7-117">See also</span></span>

- [<span data-ttu-id="18af7-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18af7-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
