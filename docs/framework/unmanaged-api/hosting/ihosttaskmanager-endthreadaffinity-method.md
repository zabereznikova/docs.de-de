---
title: IHostTaskManager::EndThreadAffinity-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb07e38542893b26595b67d6cf0fa77c522b4def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442812"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="07985-102">IHostTaskManager::EndThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="07985-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="07985-103">Benachrichtigt der Host, die von Code verwaltetem wird den Zeitraum, in dem muss die aktuelle Aufgabe nicht in einen anderen Betriebssystemthread verschoben werden, beendet nach einem vorhergegangenen Aufruf von [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="07985-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07985-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07985-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="07985-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07985-105">Return Value</span></span>  
  
|<span data-ttu-id="07985-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07985-106">HRESULT</span></span>|<span data-ttu-id="07985-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07985-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07985-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="07985-108">S_OK</span></span>|<span data-ttu-id="07985-109">`EndThreadAffinity` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="07985-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="07985-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="07985-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="07985-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="07985-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="07985-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07985-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="07985-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="07985-113">The call timed out.</span></span>|  
|<span data-ttu-id="07985-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="07985-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="07985-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="07985-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="07985-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="07985-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="07985-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="07985-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="07985-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="07985-118">E_FAIL</span></span>|<span data-ttu-id="07985-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="07985-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="07985-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="07985-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="07985-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="07985-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="07985-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="07985-122">E_UNEXPECTED</span></span>|<span data-ttu-id="07985-123">`EndThreadAffinity` wurde aufgerufen, ohne eine zuvor entsprechenden Aufruf `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="07985-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07985-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07985-124">Remarks</span></span>  
 <span data-ttu-id="07985-125">Die CLR stellt einen zugehörigen Aufruf an `BeginThreadAffinity` für die aktuelle Aufgabe vor dem Aufruf `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="07985-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="07985-126">In Ermangelung einer entsprechenden Aufruf der Host-Implementierung von [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) sollten E_UNEXPECTED zurückgegeben wird und keine Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="07985-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07985-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07985-127">Requirements</span></span>  
 <span data-ttu-id="07985-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07985-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07985-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07985-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07985-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="07985-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07985-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07985-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07985-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07985-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="07985-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07985-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="07985-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07985-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="07985-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07985-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="07985-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07985-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
