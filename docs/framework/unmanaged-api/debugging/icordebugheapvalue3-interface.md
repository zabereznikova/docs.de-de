---
title: ICorDebugHeapValue3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: a1f4964c89aa3b658c57946d4b5a0327797118f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728705"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="3cf73-102">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cf73-102">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="3cf73-103">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3cf73-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="3cf73-104">Diese Schnittstelle erweitert die ICorDebugHeapValue-und ICorDebugHeapValue2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="3cf73-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3cf73-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3cf73-105">Methods</span></span>  
  
|<span data-ttu-id="3cf73-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3cf73-106">Method</span></span>|<span data-ttu-id="3cf73-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3cf73-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3cf73-108">GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="3cf73-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="3cf73-109">Gibt den verwalteten Thread zurück, der die Monitor Sperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="3cf73-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="3cf73-110">GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="3cf73-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="3cf73-111">Stellt eine geordnete Liste von Threads bereit, die für das-Ereignis in die Warteschlange eingereiht werden, das einer Monitor Sperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3cf73-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf73-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cf73-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cf73-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3cf73-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cf73-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3cf73-114">Requirements</span></span>  

 <span data-ttu-id="3cf73-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cf73-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf73-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cf73-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cf73-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cf73-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cf73-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cf73-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf73-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cf73-119">See also</span></span>

- [<span data-ttu-id="3cf73-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3cf73-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3cf73-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3cf73-121">Debugging</span></span>](index.md)
