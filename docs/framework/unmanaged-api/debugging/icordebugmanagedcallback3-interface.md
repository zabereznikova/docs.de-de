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
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793272"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="2f072-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f072-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="2f072-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="2f072-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f072-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2f072-104">Methods</span></span>  
  
|<span data-ttu-id="2f072-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="2f072-105">Method</span></span>|<span data-ttu-id="2f072-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f072-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f072-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="2f072-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="2f072-108">Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="2f072-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f072-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f072-109">Remarks</span></span>  
 <span data-ttu-id="2f072-110">Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2f072-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f072-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2f072-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f072-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f072-112">Requirements</span></span>  
 <span data-ttu-id="2f072-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f072-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f072-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f072-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f072-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f072-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f072-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f072-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f072-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f072-117">See also</span></span>

- [<span data-ttu-id="2f072-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f072-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="2f072-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f072-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="2f072-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2f072-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2f072-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2f072-121">Debugging</span></span>](index.md)
