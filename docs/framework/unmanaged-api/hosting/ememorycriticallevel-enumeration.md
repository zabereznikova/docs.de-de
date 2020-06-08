---
title: EMemoryCriticalLevel-Enumeration
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 359dd84032fce920892631dda2615f63aa54fa6b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504380"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="50572-102">EMemoryCriticalLevel-Enumeration</span><span class="sxs-lookup"><span data-stu-id="50572-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="50572-103">Enthält Werte, die die Auswirkung eines Fehlers angeben, wenn eine bestimmte Speicher Belegung angefordert wurde, jedoch nicht erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="50572-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50572-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50572-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="50572-105">Member</span><span class="sxs-lookup"><span data-stu-id="50572-105">Members</span></span>  
  
|<span data-ttu-id="50572-106">Member</span><span class="sxs-lookup"><span data-stu-id="50572-106">Member</span></span>|<span data-ttu-id="50572-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50572-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="50572-108">Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code in der Domäne, die die Zuordnung angefordert hat, wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="50572-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="50572-109">Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht sicherstellen, dass die Domäne weiterhin verwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="50572-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="50572-110">Der Host entscheidet, welche Aktion ausgeführt werden soll, wenn die Zuordnung nicht erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="50572-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="50572-111">Sie kann die CLR anweisen, den automatisch abzubrechen `AppDomain` , oder die Ausführung durch Aufrufen von Methoden für [ICLRPolicyManager](iclrpolicymanager-interface.md)fortsetzen lassen.</span><span class="sxs-lookup"><span data-stu-id="50572-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="50572-112">Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code im Prozess wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="50572-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="50572-113">Dieser Wert wird beim Start und beim Ausführen von Finalizern verwendet.</span><span class="sxs-lookup"><span data-stu-id="50572-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="50572-114">Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht in diesem Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="50572-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="50572-115">Wenn die Zuordnung fehlschlägt, wird die CLR effektiv deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="50572-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="50572-116">Alle nachfolgenden Aufrufe der CLR schlagen mit HOST_E_CLRNOTAVAILABLE fehl.</span><span class="sxs-lookup"><span data-stu-id="50572-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="50572-117">Gibt an, dass die Zuordnung für die Ausführung der Aufgabe, die die Zuordnung angefordert hat, wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="50572-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="50572-118">Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht garantieren, dass der Task ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="50572-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="50572-119">Im Fall eines Fehlers löst die CLR eine <xref:System.Threading.ThreadAbortException> auf dem physischen Vorgangs System Thread aus.</span><span class="sxs-lookup"><span data-stu-id="50572-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50572-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="50572-120">Remarks</span></span>  
 <span data-ttu-id="50572-121">Die in den Schnittstellen [IHostMemoryManager](ihostmemorymanager-interface.md) und [IHostMAlloc](ihostmalloc-interface.md) definierten Speicher Belegungs Methoden akzeptieren einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="50572-121">The memory allocation methods defined in the [IHostMemoryManager](ihostmemorymanager-interface.md) and [IHostMAlloc](ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="50572-122">Je nach Schweregrad eines Fehlers kann ein Host entscheiden, ob die Zuordnungs Anforderung sofort fehlschlagen soll oder ob gewartet werden kann, bis Sie erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="50572-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50572-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="50572-123">Requirements</span></span>  
 <span data-ttu-id="50572-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50572-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50572-125">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="50572-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50572-126">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="50572-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50572-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50572-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50572-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="50572-128">See also</span></span>

- [<span data-ttu-id="50572-129">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50572-129">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="50572-130">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="50572-130">Hosting Enumerations</span></span>](hosting-enumerations.md)
