---
title: ICorDebugManagedCallback::ExitProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff80462c722a84ef68ac8c6703ded3e7138a1939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="e36dc-102">ICorDebugManagedCallback::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e36dc-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="e36dc-103">Benachrichtigt den Debugger, dass ein Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e36dc-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e36dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e36dc-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e36dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e36dc-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e36dc-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="e36dc-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e36dc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e36dc-107">Remarks</span></span>  
 <span data-ttu-id="e36dc-108">Sie können nicht fortgesetzt werden, aus einer `ExitProcess` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e36dc-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="e36dc-109">Dieses Ereignis kann asynchron mit anderen Ereignissen ausgelöst werden, während der Prozess wird beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e36dc-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="e36dc-110">Dies kann auftreten, wenn der Prozess beendet wird, während angehalten, in der Regel aufgrund von einigen externen erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e36dc-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="e36dc-111">Wenn die common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis bis verzögert werden, nachdem dieser Rückruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e36dc-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="e36dc-112">Die `ExitProcess` Ereignis ist das einzige Beenden/Unload-Ereignis, der beim Herunterfahren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e36dc-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e36dc-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e36dc-113">Requirements</span></span>  
 <span data-ttu-id="e36dc-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e36dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e36dc-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e36dc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e36dc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e36dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e36dc-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e36dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36dc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e36dc-118">See Also</span></span>  
 [<span data-ttu-id="e36dc-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e36dc-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
