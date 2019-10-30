---
title: IHostTaskManager::BeginThreadAffinity-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
ms.openlocfilehash: 7c157cf27d2fe86288024a6c35e6dcbea3c46347
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133104"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="7cdfe-102">IHostTaskManager::BeginThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="7cdfe-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="7cdfe-103">Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht in einen anderen Betriebssystem Thread verschoben werden darf.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cdfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cdfe-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7cdfe-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cdfe-105">Return Value</span></span>  
  
|<span data-ttu-id="7cdfe-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cdfe-106">HRESULT</span></span>|<span data-ttu-id="7cdfe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cdfe-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cdfe-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cdfe-108">S_OK</span></span>|<span data-ttu-id="7cdfe-109">`BeginThreadAffinity` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="7cdfe-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cdfe-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cdfe-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cdfe-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cdfe-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cdfe-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-113">The call timed out.</span></span>|  
|<span data-ttu-id="7cdfe-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cdfe-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cdfe-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cdfe-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cdfe-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cdfe-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cdfe-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cdfe-118">E_FAIL</span></span>|<span data-ttu-id="7cdfe-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cdfe-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cdfe-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cdfe-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cdfe-122">Remarks</span></span>  
 <span data-ttu-id="7cdfe-123">Die CLR ruft in der Regel `IHostTaskManager::BeginThreadAffinity` im Kontext eines Aufrufs von <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>auf.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7cdfe-124">Die aktuelle Aufgabe darf nicht neu geplant werden, bis ein entsprechender-Rückruf an [IHostTaskManager:: endthreadaffinität](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="7cdfe-125">Tasks können ausgelagert werden, aber wenn Sie wieder in gewechselt werden, müssen Sie demselben Betriebssystem Thread zugewiesen werden, von dem Sie gewechselt wurden. Für `BeginThreadAffinity` werden keine Auswirkungen, da der Aufruf auf die aktuelle Aufgabe verweist.</span><span class="sxs-lookup"><span data-stu-id="7cdfe-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cdfe-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cdfe-126">Requirements</span></span>  
 <span data-ttu-id="7cdfe-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cdfe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cdfe-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7cdfe-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cdfe-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7cdfe-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cdfe-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cdfe-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cdfe-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cdfe-131">See also</span></span>

- [<span data-ttu-id="7cdfe-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cdfe-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7cdfe-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cdfe-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7cdfe-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cdfe-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7cdfe-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cdfe-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
