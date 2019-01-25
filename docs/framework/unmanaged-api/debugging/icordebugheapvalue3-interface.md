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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08a9bc8aa4aa70ad6b01c58abccd145ae43d8a52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568291"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="1b056-102">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b056-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="1b056-103">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b056-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="1b056-104">Diese Schnittstelle erweitert die ICorDebugHeapValue und ICorDebugHeapValue2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b056-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b056-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1b056-105">Methods</span></span>  
  
|<span data-ttu-id="1b056-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1b056-106">Method</span></span>|<span data-ttu-id="1b056-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b056-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b056-108">GetThreadOwningMonitorLock-Methode</span><span class="sxs-lookup"><span data-stu-id="1b056-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="1b056-109">Gibt zurück, den verwalteten Thread, der die Monitorsperre für dieses Objekt besitzt.</span><span class="sxs-lookup"><span data-stu-id="1b056-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="1b056-110">GetMonitorEventWaitList-Methode</span><span class="sxs-lookup"><span data-stu-id="1b056-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="1b056-111">Enthält eine geordnete Liste von Threads, die in die Warteschlange eingereiht werden auf das Ereignis, das eine Sperre für die Überwachung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1b056-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b056-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b056-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b056-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b056-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b056-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b056-114">Requirements</span></span>  
 <span data-ttu-id="1b056-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b056-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b056-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b056-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b056-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b056-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b056-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b056-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b056-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b056-119">See also</span></span>
- [<span data-ttu-id="1b056-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b056-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1b056-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1b056-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
