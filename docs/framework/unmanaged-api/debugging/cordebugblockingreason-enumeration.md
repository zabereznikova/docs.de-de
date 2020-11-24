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
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672850"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="eeb57-102">CorDebugBlockingReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="eeb57-102">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="eeb57-103">Gibt die möglichen Ursachen für das Blockieren eines Threads bei einem angegebenen Objekt an.</span><span class="sxs-lookup"><span data-stu-id="eeb57-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeb57-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="eeb57-105">Member</span><span class="sxs-lookup"><span data-stu-id="eeb57-105">Members</span></span>  
  
|<span data-ttu-id="eeb57-106">Member</span><span class="sxs-lookup"><span data-stu-id="eeb57-106">Member</span></span>|<span data-ttu-id="eeb57-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eeb57-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="eeb57-108">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="eeb57-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="eeb57-109">Ein Thread versucht, den kritischen Abschnitt abzurufen, der der Überwachungs Sperre eines Objekts zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eeb57-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="eeb57-110">Dies tritt normalerweise auf, wenn Sie eine der-oder-Methoden aufzurufen <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="eeb57-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="eeb57-111">Ein Thread wartet auf das Ereignis, das einer Monitor Sperre für ein Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eeb57-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="eeb57-112">Dies tritt normalerweise auf, wenn Sie eine der-Methoden aufzurufen <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` .</span><span class="sxs-lookup"><span data-stu-id="eeb57-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb57-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eeb57-113">Remarks</span></span>  

 <span data-ttu-id="eeb57-114">Wenn das-Element oder das-Element `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` in einer [corunbugblockingobject](cordebugblockingobject-structure.md) -Struktur verwendet wird, verweist der- `pBlockingObject` Member der-Struktur auf eine ICorDebug Value-Schnittstelle, die das Objekt darstellt, das eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eeb57-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="eeb57-115">Außerdem wird sichergestellt, dass die [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) -Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="eeb57-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb57-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eeb57-116">Requirements</span></span>  

 <span data-ttu-id="eeb57-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeb57-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb57-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeb57-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeb57-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeb57-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeb57-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb57-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb57-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eeb57-121">See also</span></span>

- [<span data-ttu-id="eeb57-122">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="eeb57-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="eeb57-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="eeb57-123">Debugging</span></span>](index.md)
