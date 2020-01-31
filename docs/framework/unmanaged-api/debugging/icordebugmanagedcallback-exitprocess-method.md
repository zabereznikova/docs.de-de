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
ms.openlocfilehash: 4380b8a3803e164aab7318821a9dbde32ecc3a0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781742"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="49b3e-102">ICorDebugManagedCallback::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="49b3e-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="49b3e-103">Benachrichtigt den Debugger, dass ein Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="49b3e-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49b3e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b3e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="49b3e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="49b3e-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="49b3e-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b3e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49b3e-107">Remarks</span></span>  
 <span data-ttu-id="49b3e-108">Die Fortsetzung eines `ExitProcess` Ereignisses ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="49b3e-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="49b3e-109">Dieses Ereignis wird möglicherweise asynchron für andere Ereignisse ausgelöst, während der Prozess scheinbar beendet ist.</span><span class="sxs-lookup"><span data-stu-id="49b3e-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="49b3e-110">Dies kann vorkommen, wenn der Prozess beendet wird, in der Regel aufgrund externer Kraft.</span><span class="sxs-lookup"><span data-stu-id="49b3e-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="49b3e-111">Wenn die Common Language Runtime (CLR) bereits einen verwalteten Rückruf sendet, wird dieses Ereignis verzögert, bis dieser Rückruf zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="49b3e-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="49b3e-112">Das `ExitProcess` Ereignis ist das einzige Ereignis zum Beenden/entladen, das beim Herunterfahren garantiert aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="49b3e-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b3e-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49b3e-113">Requirements</span></span>  
 <span data-ttu-id="49b3e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b3e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b3e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49b3e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49b3e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49b3e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49b3e-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b3e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b3e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49b3e-118">See also</span></span>

- [<span data-ttu-id="49b3e-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b3e-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
