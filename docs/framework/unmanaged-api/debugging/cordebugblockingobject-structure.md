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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7db321b32657087b791758096c692f25f3d7f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407835"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="a5875-102">CorDebugBlockingObject-Struktur</span><span class="sxs-lookup"><span data-stu-id="a5875-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="a5875-103">Definiert ein Objekt, das blockiert einen Thread und die spezifische Ursache, dass der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="a5875-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5875-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5875-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="a5875-105">Member</span><span class="sxs-lookup"><span data-stu-id="a5875-105">Members</span></span>  
  
|<span data-ttu-id="a5875-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5875-106">Member</span></span>|<span data-ttu-id="a5875-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5875-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="a5875-108">Das Objekt, auf dem der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a5875-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="a5875-109">Dieses Objekt ist nur für die Dauer des aktuellen Status "synchronisiert" gültig.</span><span class="sxs-lookup"><span data-stu-id="a5875-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="a5875-110">Wenn zwei Threads für das gleiche Objekt im gleichen Status "synchronisiert" blockiert werden, erwarten Sie möglicherweise die [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) Methode, um den gleichen Wert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a5875-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="a5875-111">Jedoch die Schnittstellen können oder möglicherweise nicht Zeiger entspricht.</span><span class="sxs-lookup"><span data-stu-id="a5875-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="a5875-112">Die Anzahl der Millisekunden, bevor der blockierende Vorgang tritt ein Timeout oder den Wert ' INFINITE, d. h. es wird kein Timeout. Der Timeoutwert gibt die Gesamtlänge des blockierenden Vorgangs nicht die Zeit, die noch verbleibenden Zeit an.</span><span class="sxs-lookup"><span data-stu-id="a5875-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="a5875-113">Der Grund für dieses Objekt der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="a5875-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5875-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5875-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5875-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5875-115">Requirements</span></span>  
 <span data-ttu-id="a5875-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5875-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5875-117">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a5875-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a5875-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5875-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5875-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5875-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5875-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5875-120">See Also</span></span>  
 [<span data-ttu-id="a5875-121">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="a5875-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a5875-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a5875-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
