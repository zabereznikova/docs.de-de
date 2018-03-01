---
title: IHostTask::Join-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 85ee44fe9185364a6870b996ca98cfe6cc297bf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="ffe39-102">IHostTask::Join-Methode</span><span class="sxs-lookup"><span data-stu-id="ffe39-102">IHostTask::Join Method</span></span>
<span data-ttu-id="ffe39-103">Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz abgeschlossen hat, kann das angegebene Zeitintervall abläuft, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ffe39-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffe39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffe39-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffe39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ffe39-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="ffe39-106">[in] Das Zeitintervall in Millisekunden, bis zum Beenden des Tasks.</span><span class="sxs-lookup"><span data-stu-id="ffe39-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="ffe39-107">Wenn dieses Intervall abläuft, bevor die Aufgabe beendet wird, hebt die Blockierung der aufrufenden Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="ffe39-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="ffe39-108">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="ffe39-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="ffe39-109">Ein WAIT_ALERTABLE weist der Host die Aufgabe bei aktiviert `Alert` wird aufgerufen, bevor `milliseconds` abläuft.</span><span class="sxs-lookup"><span data-stu-id="ffe39-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffe39-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ffe39-110">Return Value</span></span>  
  
|<span data-ttu-id="ffe39-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffe39-111">HRESULT</span></span>|<span data-ttu-id="ffe39-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ffe39-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffe39-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffe39-113">S_OK</span></span>|<span data-ttu-id="ffe39-114">`Join`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ffe39-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="ffe39-115">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ffe39-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffe39-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ffe39-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffe39-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffe39-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffe39-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ffe39-118">The call timed out.</span></span>|  
|<span data-ttu-id="ffe39-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffe39-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffe39-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ffe39-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffe39-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffe39-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffe39-122">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber wartete auf, oder die aktuelle `IHostTask` Instanz ist nicht mit einem Vorgang verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ffe39-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="ffe39-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffe39-123">E_FAIL</span></span>|<span data-ttu-id="ffe39-124">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ffe39-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffe39-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ffe39-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffe39-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ffe39-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffe39-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ffe39-127">Requirements</span></span>  
 <span data-ttu-id="ffe39-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe39-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe39-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffe39-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffe39-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ffe39-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffe39-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe39-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe39-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffe39-132">See Also</span></span>  
 [<span data-ttu-id="ffe39-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe39-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ffe39-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe39-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ffe39-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe39-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ffe39-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe39-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ffe39-137">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ffe39-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
