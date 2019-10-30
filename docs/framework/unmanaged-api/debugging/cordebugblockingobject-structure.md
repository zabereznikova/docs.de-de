---
title: CorDebugBlockingObject-Struktur
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
ms.openlocfilehash: 21f90e06b3b02ebc6c97610b6edc35697601f0ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132285"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="223a2-102">CorDebugBlockingObject-Struktur</span><span class="sxs-lookup"><span data-stu-id="223a2-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="223a2-103">Definiert ein Objekt, das einen Thread blockiert, und den spezifischen Grund, aus dem der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="223a2-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="223a2-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="223a2-105">Member</span><span class="sxs-lookup"><span data-stu-id="223a2-105">Members</span></span>  
  
|<span data-ttu-id="223a2-106">Member</span><span class="sxs-lookup"><span data-stu-id="223a2-106">Member</span></span>|<span data-ttu-id="223a2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="223a2-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="223a2-108">Das Objekt, für das der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="223a2-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="223a2-109">Dieses Objekt ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.</span><span class="sxs-lookup"><span data-stu-id="223a2-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="223a2-110">Wenn zwei Threads für das gleiche Objekt innerhalb desselben synchronisierten Zustands blockieren, erwarten Sie möglicherweise, dass die [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) -Methode denselben Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="223a2-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="223a2-111">Allerdings sind die Schnittstellen möglicherweise Zeiger Äquivalent.</span><span class="sxs-lookup"><span data-stu-id="223a2-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="223a2-112">Die Anzahl von Millisekunden, bevor ein Timeout auftritt, oder der Wert ist unendlich, was darauf hinweist, dass kein Timeout auftritt. Der Timeout Wert gibt die Gesamtzeit für den blockierenden Vorgang an, nicht die Zeit, die noch übrig ist.</span><span class="sxs-lookup"><span data-stu-id="223a2-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="223a2-113">Der Grund, warum der Thread für dieses Objekt blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="223a2-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="223a2-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="223a2-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="223a2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="223a2-115">Requirements</span></span>  
 <span data-ttu-id="223a2-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="223a2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223a2-117">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="223a2-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="223a2-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="223a2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="223a2-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="223a2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223a2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="223a2-120">See also</span></span>

- [<span data-ttu-id="223a2-121">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="223a2-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="223a2-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="223a2-122">Debugging</span></span>](index.md)
