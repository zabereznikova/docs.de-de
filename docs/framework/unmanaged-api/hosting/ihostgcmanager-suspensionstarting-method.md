---
title: IHostGCManager::SuspensionStarting-Methode
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: f2b4028c78daf266e4ffecd86e6b0b30b9607d5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804816"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="e3a0c-102">IHostGCManager::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="e3a0c-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="e3a0c-103">Benachrichtigt den Host darüber, dass die Common Language Runtime (CLR) die Ausführung von Aufgaben angehalten, um eine Garbage Collection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3a0c-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e3a0c-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e3a0c-105">Return Value</span></span>  
  
|<span data-ttu-id="e3a0c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3a0c-106">HRESULT</span></span>|<span data-ttu-id="e3a0c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3a0c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3a0c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3a0c-108">S_OK</span></span>|<span data-ttu-id="e3a0c-109">`SuspensionStarting`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="e3a0c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3a0c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3a0c-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3a0c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3a0c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3a0c-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-113">The call timed out.</span></span>|  
|<span data-ttu-id="e3a0c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3a0c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3a0c-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3a0c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3a0c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3a0c-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3a0c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3a0c-118">E_FAIL</span></span>|<span data-ttu-id="e3a0c-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3a0c-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3a0c-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3a0c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3a0c-122">Remarks</span></span>  
 <span data-ttu-id="e3a0c-123">Die CLR ruft `SuspensionStarting` auf, um den Host darüber zu informieren, dass Garbage Collection auftritt.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e3a0c-124">Planen Sie diese Aufgabe nicht neu.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-124">Do not reschedule this task.</span></span> <span data-ttu-id="e3a0c-125">Der Host muss einen Task neu planen, wenn [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a0c-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3a0c-126">Requirements</span></span>  
 <span data-ttu-id="e3a0c-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3a0c-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a0c-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e3a0c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3a0c-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e3a0c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3a0c-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a0c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a0c-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3a0c-131">See also</span></span>

- [<span data-ttu-id="e3a0c-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a0c-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e3a0c-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a0c-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e3a0c-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a0c-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e3a0c-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a0c-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e3a0c-136">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3a0c-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
