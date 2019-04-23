---
title: CorDebugBlockingReason-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54652727b4684d71068a19eb5eeb2e862f413f25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215078"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="dae6e-102">CorDebugBlockingReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dae6e-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="dae6e-103">Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.</span><span class="sxs-lookup"><span data-stu-id="dae6e-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dae6e-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="dae6e-105">Member</span><span class="sxs-lookup"><span data-stu-id="dae6e-105">Members</span></span>  
  
|<span data-ttu-id="dae6e-106">Member</span><span class="sxs-lookup"><span data-stu-id="dae6e-106">Member</span></span>|<span data-ttu-id="dae6e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dae6e-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="dae6e-108">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dae6e-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="dae6e-109">Ein Thread versucht, den kritischen Abschnitt anzufordern, der die Monitorsperre für ein Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dae6e-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="dae6e-110">In der Regel tritt dies auf, wenn eine Aufrufen der <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> oder <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> Methoden.</span><span class="sxs-lookup"><span data-stu-id="dae6e-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="dae6e-111">Ein Thread wartet auf das Ereignis, das mit einer Monitorsperre für ein Objekt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="dae6e-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="dae6e-112">In der Regel tritt dies auf, wenn eine Aufrufen der <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` Methoden.</span><span class="sxs-lookup"><span data-stu-id="dae6e-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dae6e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dae6e-113">Remarks</span></span>  
 <span data-ttu-id="dae6e-114">Wenn die `BLOCKING_MONITOR_CRITICAL_SECTION` oder `BLOCKING_MONITOR_EVENT` Member wird verwendet, eine [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur, die `pBlockingObject` Member der Struktur-verweist auf eine "ICorDebugValue"-Schnittstelle, die das Objekt darstellt, die aufgerufen wird .</span><span class="sxs-lookup"><span data-stu-id="dae6e-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="dae6e-115">Es ist auch sichergestellt, implementieren die [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dae6e-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae6e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dae6e-116">Requirements</span></span>  
 <span data-ttu-id="dae6e-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae6e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae6e-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dae6e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dae6e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dae6e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dae6e-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae6e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae6e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dae6e-121">See also</span></span>

- [<span data-ttu-id="dae6e-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="dae6e-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="dae6e-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="dae6e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
