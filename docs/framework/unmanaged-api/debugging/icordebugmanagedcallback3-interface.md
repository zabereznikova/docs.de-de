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
ms.openlocfilehash: 63e3f166c4cbf17f4892dccf770343bfbf6e0284
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209746"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="6ebf2-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ebf2-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="6ebf2-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="6ebf2-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ebf2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6ebf2-104">Methods</span></span>  
  
|<span data-ttu-id="6ebf2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6ebf2-105">Method</span></span>|<span data-ttu-id="6ebf2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ebf2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ebf2-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="6ebf2-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="6ebf2-108">Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="6ebf2-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ebf2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ebf2-109">Remarks</span></span>  
 <span data-ttu-id="6ebf2-110">Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6ebf2-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ebf2-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6ebf2-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ebf2-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6ebf2-112">Requirements</span></span>  
 <span data-ttu-id="6ebf2-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ebf2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ebf2-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ebf2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ebf2-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ebf2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ebf2-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ebf2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ebf2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ebf2-117">See also</span></span>

- [<span data-ttu-id="6ebf2-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ebf2-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="6ebf2-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ebf2-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="6ebf2-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6ebf2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6ebf2-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6ebf2-121">Debugging</span></span>](index.md)
