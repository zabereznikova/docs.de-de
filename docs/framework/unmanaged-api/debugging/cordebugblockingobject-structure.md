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
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143220"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="c7250-102">CorDebugBlockingObject-Struktur</span><span class="sxs-lookup"><span data-stu-id="c7250-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="c7250-103">Definiert ein Objekt, das blockiert einen Thread und die spezifische Ursache, dass der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="c7250-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7250-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7250-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="c7250-105">Member</span><span class="sxs-lookup"><span data-stu-id="c7250-105">Members</span></span>  
  
|<span data-ttu-id="c7250-106">Member</span><span class="sxs-lookup"><span data-stu-id="c7250-106">Member</span></span>|<span data-ttu-id="c7250-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7250-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="c7250-108">Das Objekt, auf dem der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7250-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="c7250-109">Dieses Objekt gilt nur für die Dauer des aktuellen Status "synchronisiert".</span><span class="sxs-lookup"><span data-stu-id="c7250-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="c7250-110">Wenn zwei Threads für dasselbe Objekt innerhalb der gleichen Status "synchronisiert" blockiert werden, erwarten Sie möglicherweise die [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) Methode, um den gleichen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7250-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="c7250-111">Allerdings werden die Schnittstellen können oder möglicherweise keine äquivalente Zeiger.</span><span class="sxs-lookup"><span data-stu-id="c7250-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="c7250-112">Die Anzahl der Millisekunden, bevor der blockierende Vorgang wird das Timeout, oder der Wert INFINITE, der angibt, dass es kein Timeout. Der Timeout-Wert gibt die Gesamtlänge der blockierende Vorgang, nicht die Zeit, die noch verbleibenden ist.</span><span class="sxs-lookup"><span data-stu-id="c7250-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="c7250-113">Der Grund für dieses Objekt der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="c7250-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7250-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7250-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7250-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7250-115">Requirements</span></span>  
 <span data-ttu-id="c7250-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7250-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7250-117">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="c7250-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="c7250-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7250-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7250-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7250-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7250-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7250-120">See also</span></span>

- [<span data-ttu-id="c7250-121">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c7250-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="c7250-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c7250-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
