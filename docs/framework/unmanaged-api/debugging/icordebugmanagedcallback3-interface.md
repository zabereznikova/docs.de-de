---
title: ICorDebugManagedCallback3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3
helpviewer_keywords: ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2f24cc8fbd8533ef6717bc1dcd1baab0ea9ab45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="51899-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51899-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="51899-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="51899-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51899-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="51899-104">Methods</span></span>  
  
|<span data-ttu-id="51899-105">Methode</span><span class="sxs-lookup"><span data-stu-id="51899-105">Method</span></span>|<span data-ttu-id="51899-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51899-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51899-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="51899-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="51899-108">Gibt an, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="51899-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51899-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51899-109">Remarks</span></span>  
 <span data-ttu-id="51899-110">Diese Schnittstelle ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) und [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="51899-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51899-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="51899-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51899-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51899-112">Requirements</span></span>  
 <span data-ttu-id="51899-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51899-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51899-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51899-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51899-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51899-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51899-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51899-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51899-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51899-117">See Also</span></span>  
 [<span data-ttu-id="51899-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51899-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="51899-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51899-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="51899-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="51899-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="51899-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="51899-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
