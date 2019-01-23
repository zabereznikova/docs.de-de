---
title: ICLRTask::NeedsPriorityScheduling-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2a26e32040f705fd46f9d9d8909fd47e963baa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510780"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="2e14d-102">ICLRTask::NeedsPriorityScheduling-Methode</span><span class="sxs-lookup"><span data-stu-id="2e14d-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="2e14d-103">Ruft einen Wert, der angibt, ob die aktuelle Aufgabe, die ausgelagert werden wird, muss eine hohe Priorität für die durch das erneute Planen markiert sein.</span><span class="sxs-lookup"><span data-stu-id="2e14d-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e14d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e14d-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e14d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e14d-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="2e14d-106">[out] `true`, wenn der Host erfolgen, die aktuelle Aufgabeninstanz erneut zu planen, so bald wie möglich ist, andernfalls soll `false`.</span><span class="sxs-lookup"><span data-stu-id="2e14d-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e14d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e14d-107">Return Value</span></span>  
  
|<span data-ttu-id="2e14d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e14d-108">HRESULT</span></span>|<span data-ttu-id="2e14d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e14d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e14d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e14d-110">S_OK</span></span>|<span data-ttu-id="2e14d-111">`NeedsPriorityRescheduling` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2e14d-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="2e14d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e14d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e14d-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e14d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e14d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e14d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e14d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e14d-115">The call timed out.</span></span>|  
|<span data-ttu-id="2e14d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e14d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e14d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2e14d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e14d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e14d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e14d-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="2e14d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e14d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e14d-120">E_FAIL</span></span>|<span data-ttu-id="2e14d-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e14d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e14d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e14d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e14d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2e14d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e14d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e14d-124">Remarks</span></span>  
 <span data-ttu-id="2e14d-125">In Situationen, in dem die Aufgabe besteht in der Nähe, der vom Garbage Collector erfasst wird, legt die CLR den Wert der `pbNeedsPriorityScheduling` zu `true`, der angibt, durch das erneute Planen hoher Priorität.</span><span class="sxs-lookup"><span data-stu-id="2e14d-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="2e14d-126">Dies ermöglicht den Host, den Task schnell erneut zu planen und das Potenzial für Verzögerungen bei der Garbage collection minimiert, und aktivieren den Host und die Laufzeitumgebung arbeiten zusammen, um Arbeitsspeicher zu sparen.</span><span class="sxs-lookup"><span data-stu-id="2e14d-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e14d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e14d-127">Requirements</span></span>  
 <span data-ttu-id="2e14d-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e14d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e14d-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e14d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e14d-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2e14d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e14d-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e14d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e14d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e14d-132">See also</span></span>
- [<span data-ttu-id="2e14d-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e14d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2e14d-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e14d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2e14d-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e14d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2e14d-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e14d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
