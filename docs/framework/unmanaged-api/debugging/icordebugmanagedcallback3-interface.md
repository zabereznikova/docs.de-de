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
ms.openlocfilehash: ab1dab753728102fc27e39c3ed64bf776e2e5ad5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634469"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="f67fa-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f67fa-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="f67fa-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f67fa-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f67fa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f67fa-104">Methods</span></span>  
  
|<span data-ttu-id="f67fa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f67fa-105">Method</span></span>|<span data-ttu-id="f67fa-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f67fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f67fa-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="f67fa-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="f67fa-108">Gibt an, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f67fa-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f67fa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f67fa-109">Remarks</span></span>  
 <span data-ttu-id="f67fa-110">Diese Schnittstelle ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) und [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="f67fa-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f67fa-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f67fa-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f67fa-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f67fa-112">Requirements</span></span>  
 <span data-ttu-id="f67fa-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f67fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f67fa-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f67fa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f67fa-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f67fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f67fa-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f67fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f67fa-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f67fa-117">See also</span></span>
- [<span data-ttu-id="f67fa-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f67fa-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="f67fa-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f67fa-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f67fa-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f67fa-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f67fa-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f67fa-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
