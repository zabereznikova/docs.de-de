---
title: ICorDebugManagedCallback::ExitProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7be74520fff65b113f54d82305a84dd183286876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="0ad6d-102">ICorDebugManagedCallback::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="0ad6d-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="0ad6d-103">Benachrichtigt den Debugger, dass ein Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ad6d-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ad6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ad6d-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0ad6d-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad6d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ad6d-107">Remarks</span></span>  
 <span data-ttu-id="0ad6d-108">Sie können nicht fortgesetzt werden, aus einer `ExitProcess` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="0ad6d-109">Dieses Ereignis kann asynchron mit anderen Ereignissen ausgelöst werden, während der Prozess wird beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="0ad6d-110">Dies kann auftreten, wenn der Prozess beendet wird, während angehalten, in der Regel aufgrund von einigen externen erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="0ad6d-111">Wenn die common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis bis verzögert werden, nachdem dieser Rückruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="0ad6d-112">Die `ExitProcess` Ereignis ist das einzige Beenden/Unload-Ereignis, der beim Herunterfahren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad6d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ad6d-113">Requirements</span></span>  
 <span data-ttu-id="0ad6d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad6d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad6d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ad6d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ad6d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad6d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad6d-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad6d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad6d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ad6d-118">See Also</span></span>  
 [<span data-ttu-id="0ad6d-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad6d-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
