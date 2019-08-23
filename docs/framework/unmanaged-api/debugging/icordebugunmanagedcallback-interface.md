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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a34454e7e007b4eba557c712cb824362aa5047c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952976"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="1b937-102">ICorDebugUnmanagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b937-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="1b937-103">Stellt Benachrichtigungen zu systemeigenen Ereignissen bereit, die nicht direkt mit dem Common Language Runtime (CLR) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="1b937-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b937-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1b937-104">Methods</span></span>  
  
|<span data-ttu-id="1b937-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1b937-105">Method</span></span>|<span data-ttu-id="1b937-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b937-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b937-107">DebugEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="1b937-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="1b937-108">Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1b937-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b937-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b937-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b937-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b937-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b937-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b937-111">Requirements</span></span>  
 <span data-ttu-id="1b937-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b937-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b937-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1b937-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b937-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b937-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b937-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b937-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b937-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b937-116">See also</span></span>

- [<span data-ttu-id="1b937-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b937-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
