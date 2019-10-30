---
title: ICorDebugUnmanagedCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: 6de440d10f02f177e62ca3d2bd29fd5e98ea9388
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137142"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="12ad3-102">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12ad3-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="12ad3-103">Stellt Benachrichtigungen zu systemeigenen Ereignissen bereit, die nicht direkt mit dem Common Language Runtime (CLR) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="12ad3-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12ad3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="12ad3-104">Methods</span></span>  
  
|<span data-ttu-id="12ad3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="12ad3-105">Method</span></span>|<span data-ttu-id="12ad3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12ad3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12ad3-107">DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="12ad3-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="12ad3-108">Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="12ad3-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12ad3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12ad3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12ad3-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="12ad3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12ad3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12ad3-111">Requirements</span></span>  
 <span data-ttu-id="12ad3-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12ad3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12ad3-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12ad3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12ad3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12ad3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12ad3-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12ad3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ad3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12ad3-116">See also</span></span>

- [<span data-ttu-id="12ad3-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="12ad3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
