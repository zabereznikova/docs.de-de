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
ms.openlocfilehash: 04b8ac6751024e64cc866fce1cfe72fb42e41200
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760436"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="856f6-102">ICorDebugManagedCallback::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="856f6-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="856f6-103">Benachrichtigt den Debugger an, dass ein Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="856f6-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="856f6-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="856f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="856f6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="856f6-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="856f6-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="856f6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="856f6-107">Remarks</span></span>  
 <span data-ttu-id="856f6-108">Sie können nicht fortgesetzt werden, von einem `ExitProcess` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="856f6-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="856f6-109">Dieses Ereignis kann asynchron mit anderen Ereignissen ausgelöst werden, während der Prozess angezeigt wird, beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="856f6-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="856f6-110">Dies kann auftreten, wenn der Prozess beendet wird, während angehalten, in der Regel aufgrund von einigen externen erzwingen.</span><span class="sxs-lookup"><span data-stu-id="856f6-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="856f6-111">Wenn die common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis bis verzögert werden, nachdem dieser Rückruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="856f6-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="856f6-112">Die `ExitProcess` Ereignis ist das einzige Beenden/Entladen-Ereignis, die mit Sicherheit beim Herunterfahren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="856f6-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="856f6-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="856f6-113">Requirements</span></span>  
 <span data-ttu-id="856f6-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856f6-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="856f6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="856f6-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="856f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="856f6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="856f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856f6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="856f6-118">See also</span></span>

- [<span data-ttu-id="856f6-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="856f6-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
