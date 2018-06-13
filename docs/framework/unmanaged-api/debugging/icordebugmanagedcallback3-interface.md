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
ms.openlocfilehash: 6aab35aa5580b53dda513369066ff77f55230265
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419850"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="a37d0-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a37d0-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="a37d0-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a37d0-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a37d0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a37d0-104">Methods</span></span>  
  
|<span data-ttu-id="a37d0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a37d0-105">Method</span></span>|<span data-ttu-id="a37d0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a37d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a37d0-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="a37d0-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="a37d0-108">Gibt an, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a37d0-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a37d0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a37d0-109">Remarks</span></span>  
 <span data-ttu-id="a37d0-110">Diese Schnittstelle ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) und [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a37d0-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a37d0-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a37d0-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a37d0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a37d0-112">Requirements</span></span>  
 <span data-ttu-id="a37d0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a37d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a37d0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a37d0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a37d0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a37d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a37d0-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a37d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a37d0-117">See Also</span></span>  
 [<span data-ttu-id="a37d0-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a37d0-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="a37d0-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a37d0-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="a37d0-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a37d0-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a37d0-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a37d0-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
