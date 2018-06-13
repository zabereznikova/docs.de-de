---
title: ICorDebugManagedCallback::ExitProcess-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42330296defe90980dd431ce39765a549057b82a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416880"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="ab1db-102">ICorDebugManagedCallback::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ab1db-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="ab1db-103">Benachrichtigt den Debugger, dass ein Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab1db-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab1db-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab1db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab1db-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ab1db-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="ab1db-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab1db-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab1db-107">Remarks</span></span>  
 <span data-ttu-id="ab1db-108">Sie können nicht fortgesetzt werden, aus einer `ExitProcess` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ab1db-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="ab1db-109">Dieses Ereignis kann asynchron mit anderen Ereignissen ausgelöst werden, während der Prozess wird beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab1db-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="ab1db-110">Dies kann auftreten, wenn der Prozess beendet wird, während angehalten, in der Regel aufgrund von einigen externen erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ab1db-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="ab1db-111">Wenn die common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis bis verzögert werden, nachdem dieser Rückruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ab1db-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="ab1db-112">Die `ExitProcess` Ereignis ist das einzige Beenden/Unload-Ereignis, der beim Herunterfahren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ab1db-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1db-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab1db-113">Requirements</span></span>  
 <span data-ttu-id="ab1db-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab1db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1db-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab1db-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab1db-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab1db-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab1db-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1db-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab1db-118">See Also</span></span>  
 [<span data-ttu-id="ab1db-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab1db-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
