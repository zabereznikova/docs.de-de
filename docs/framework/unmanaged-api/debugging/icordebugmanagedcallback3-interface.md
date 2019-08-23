---
title: ICorDebugManagedCallback3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 138ac80a9abb64d4c004e83e53ed1eea2b124ff2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909898"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="ed3b9-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3b9-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="ed3b9-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ed3b9-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed3b9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed3b9-104">Methods</span></span>  
  
|<span data-ttu-id="ed3b9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ed3b9-105">Method</span></span>|<span data-ttu-id="ed3b9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed3b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed3b9-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3b9-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="ed3b9-108">Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ed3b9-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed3b9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed3b9-109">Remarks</span></span>  
 <span data-ttu-id="ed3b9-110">Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ed3b9-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed3b9-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b9-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3b9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed3b9-112">Requirements</span></span>  
 <span data-ttu-id="ed3b9-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3b9-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="ed3b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed3b9-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed3b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed3b9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3b9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed3b9-117">See also</span></span>

- [<span data-ttu-id="ed3b9-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3b9-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="ed3b9-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3b9-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="ed3b9-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ed3b9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ed3b9-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ed3b9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
