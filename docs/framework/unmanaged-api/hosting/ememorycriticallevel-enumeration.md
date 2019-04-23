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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122290"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="e9474-102">EMemoryCriticalLevel-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e9474-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="e9474-103">Enthält Werte, die die Auswirkungen eines Fehlers angeben, wenn eine bestimmte speicherbelegung angefordert wurde, aber nicht zufrieden.</span><span class="sxs-lookup"><span data-stu-id="e9474-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9474-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9474-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="e9474-105">Member</span><span class="sxs-lookup"><span data-stu-id="e9474-105">Members</span></span>  
  
|<span data-ttu-id="e9474-106">Member</span><span class="sxs-lookup"><span data-stu-id="e9474-106">Member</span></span>|<span data-ttu-id="e9474-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9474-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="e9474-108">Gibt an, dass die Zuordnung ist wichtig für die Ausführung von verwaltetem Code in der Domäne, die die Zuordnung angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="e9474-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="e9474-109">Wenn Arbeitsspeicher zugeordnet werden kann, kann nicht die CLR nicht garantieren, dass die Domäne noch verwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="e9474-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="e9474-110">Der Host entscheidet, welche Aktion soll, wenn die Zuordnung nicht erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9474-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="e9474-111">Sie können die CLR anweisen, zum Abbrechen der `AppDomain` automatisch, oder lassen sie Sie weiterhin ausgeführt, durch Aufrufen von Methoden für [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e9474-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="e9474-112">Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code im Prozess wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="e9474-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="e9474-113">Dieser Wert wird während des Starts und bei der Ausführung von Finalizern verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9474-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="e9474-114">Wenn der Arbeitsspeicher nicht reserviert werden kann, kann nicht die CLR im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9474-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="e9474-115">Wenn die Zuordnung fehlschlägt, wird die CLR deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e9474-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="e9474-116">Alle nachfolgenden Aufrufe in die CLR schlagen mit HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e9474-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="e9474-117">Gibt an, dass die Zuordnung ist entscheidend für die Ausführung des Tasks, die die Zuordnung angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="e9474-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="e9474-118">Wenn Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht gewährleisten, dass die Aufgabe ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9474-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="e9474-119">Bei einem Fehler löst die CLR eine <xref:System.Threading.ThreadAbortException> auf dem physischen Betriebssystemthread.</span><span class="sxs-lookup"><span data-stu-id="e9474-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9474-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9474-120">Remarks</span></span>  
 <span data-ttu-id="e9474-121">Die Speicher-Zuordnung in definierten Methoden den [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) und [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) Schnittstellen akzeptieren einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="e9474-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="e9474-122">Abhängig vom Schweregrad des Fehlers, kann ein Host entscheiden Sie, ob die zuordnungsanforderung sofort fehl, oder warten, bis es erfüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9474-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9474-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9474-123">Requirements</span></span>  
 <span data-ttu-id="e9474-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9474-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9474-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9474-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9474-126">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9474-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9474-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9474-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9474-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9474-128">See also</span></span>

- [<span data-ttu-id="e9474-129">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9474-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="e9474-130">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e9474-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
