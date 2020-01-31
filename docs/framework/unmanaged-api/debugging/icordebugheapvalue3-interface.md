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
ms.openlocfilehash: ddfe8cee8fdbca910ffa4f6989b1359ae5f7b11f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794379"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="62328-102">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62328-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="62328-103">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62328-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="62328-104">Diese Schnittstelle erweitert die ICorDebugHeapValue-und ICorDebugHeapValue2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="62328-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62328-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="62328-105">Methods</span></span>  
  
|<span data-ttu-id="62328-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="62328-106">Method</span></span>|<span data-ttu-id="62328-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62328-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62328-108">GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="62328-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="62328-109">Gibt den verwalteten Thread zurück, der die Monitor Sperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="62328-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="62328-110">GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="62328-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="62328-111">Stellt eine geordnete Liste von Threads bereit, die für das-Ereignis in die Warteschlange eingereiht werden, das einer Monitor Sperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="62328-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62328-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62328-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62328-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62328-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62328-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62328-114">Requirements</span></span>  
 <span data-ttu-id="62328-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62328-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62328-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62328-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62328-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62328-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62328-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62328-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62328-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62328-119">See also</span></span>

- [<span data-ttu-id="62328-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62328-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62328-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="62328-121">Debugging</span></span>](index.md)
