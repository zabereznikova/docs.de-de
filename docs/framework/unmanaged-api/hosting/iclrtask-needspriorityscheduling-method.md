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
ms.openlocfilehash: 86e0899b883f09f2e7b27c0f957e943deb73bb66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690797"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="0f619-102">ICLRTask::NeedsPriorityScheduling-Methode</span><span class="sxs-lookup"><span data-stu-id="0f619-102">ICLRTask::NeedsPriorityScheduling Method</span></span>

<span data-ttu-id="0f619-103">Ruft einen Wert ab, der angibt, ob der aktuelle Task, der ausgeschaltet wird, als hohe Priorität für die Neuplanung gekennzeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="0f619-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f619-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f619-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f619-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f619-105">Parameters</span></span>  

 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="0f619-106">[out] `true` , wenn der Host versuchen soll, die aktuelle Task Instanz so bald wie möglich neu zu planen; andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="0f619-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f619-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f619-107">Return Value</span></span>  
  
|<span data-ttu-id="0f619-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f619-108">HRESULT</span></span>|<span data-ttu-id="0f619-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f619-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f619-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f619-110">S_OK</span></span>|<span data-ttu-id="0f619-111">`NeedsPriorityRescheduling` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f619-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="0f619-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f619-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f619-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0f619-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f619-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f619-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f619-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0f619-115">The call timed out.</span></span>|  
|<span data-ttu-id="0f619-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f619-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f619-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0f619-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f619-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f619-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f619-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="0f619-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f619-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f619-120">E_FAIL</span></span>|<span data-ttu-id="0f619-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f619-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f619-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="0f619-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f619-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0f619-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f619-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f619-124">Remarks</span></span>  

 <span data-ttu-id="0f619-125">In Fällen, in denen die Aufgabe in der Nähe ist, vom Garbage Collector gesammelt zu werden, legt die CLR den Wert von `pbNeedsPriorityScheduling` auf fest, um eine `true` Neuplanung mit hoher Priorität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f619-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="0f619-126">Dies ermöglicht es dem Host, den Task schnell neu zu planen. Dadurch wird das Potenzial für Verzögerungen in Garbage Collection minimiert, und der Host und die Laufzeit können zusammenarbeiten, um Speicherressourcen zu sparen.</span><span class="sxs-lookup"><span data-stu-id="0f619-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f619-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0f619-127">Requirements</span></span>  

 <span data-ttu-id="0f619-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f619-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f619-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0f619-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f619-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f619-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f619-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f619-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f619-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f619-132">See also</span></span>

- [<span data-ttu-id="0f619-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f619-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0f619-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f619-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0f619-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f619-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0f619-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f619-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
