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
ms.openlocfilehash: acab49097059081540ec364d7f134d31432988a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108276"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="7c17f-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c17f-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="7c17f-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="7c17f-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c17f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c17f-104">Methods</span></span>  
  
|<span data-ttu-id="7c17f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7c17f-105">Method</span></span>|<span data-ttu-id="7c17f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c17f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c17f-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="7c17f-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="7c17f-108">Gibt an, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="7c17f-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c17f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c17f-109">Remarks</span></span>  
 <span data-ttu-id="7c17f-110">Diese Schnittstelle ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) und [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="7c17f-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c17f-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7c17f-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c17f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c17f-112">Requirements</span></span>  
 <span data-ttu-id="7c17f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c17f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c17f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c17f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c17f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c17f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7c17f-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7c17f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c17f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c17f-117">See also</span></span>

- [<span data-ttu-id="7c17f-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c17f-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="7c17f-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c17f-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7c17f-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c17f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7c17f-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7c17f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
