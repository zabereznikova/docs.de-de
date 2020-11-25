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
ms.openlocfilehash: e04f5be6d2612b26bf7d71807753d170e6a5a7a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723297"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="22c19-102">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22c19-102">ICorDebugManagedCallback3 Interface</span></span>

<span data-ttu-id="22c19-103">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="22c19-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22c19-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="22c19-104">Methods</span></span>  
  
|<span data-ttu-id="22c19-105">Methode</span><span class="sxs-lookup"><span data-stu-id="22c19-105">Method</span></span>|<span data-ttu-id="22c19-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22c19-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22c19-107">CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="22c19-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="22c19-108">Gibt an, dass eine aktivierte benutzerdefinierte Debugger-Benachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="22c19-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22c19-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22c19-109">Remarks</span></span>  

 <span data-ttu-id="22c19-110">Diese Schnittstelle ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle und der [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22c19-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22c19-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22c19-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22c19-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22c19-112">Requirements</span></span>  

 <span data-ttu-id="22c19-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22c19-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c19-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22c19-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22c19-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22c19-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22c19-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22c19-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c19-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22c19-117">See also</span></span>

- [<span data-ttu-id="22c19-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22c19-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="22c19-119">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22c19-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="22c19-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="22c19-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="22c19-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="22c19-121">Debugging</span></span>](index.md)
