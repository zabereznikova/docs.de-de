---
title: IHostTask::Join-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4373fc4e8a4c414c40e8d3c5547b5998b9300348
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170759"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="4989d-102">IHostTask::Join-Methode</span><span class="sxs-lookup"><span data-stu-id="4989d-102">IHostTask::Join Method</span></span>
<span data-ttu-id="4989d-103">Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz abgeschlossen wurde, wird das angegebene Zeitintervall abgelaufen ist, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4989d-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4989d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4989d-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4989d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4989d-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="4989d-106">[in] Das Zeitintervall in Millisekunden, für die Aufgabe beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4989d-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="4989d-107">Wenn dieses Intervall abläuft, bevor die Aufgabe beendet wird, hebt die Blockierung der aufrufenden Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="4989d-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="4989d-108">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="4989d-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="4989d-109">WAIT_ALERTABLE Wert weist den Host an der Aufgabe zu aktivieren, wenn `Alert` wird aufgerufen, bevor `milliseconds` abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="4989d-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4989d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4989d-110">Return Value</span></span>  
  
|<span data-ttu-id="4989d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4989d-111">HRESULT</span></span>|<span data-ttu-id="4989d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4989d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4989d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4989d-113">S_OK</span></span>|`Join` <span data-ttu-id="4989d-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4989d-114">returned successfully.</span></span>|  
|<span data-ttu-id="4989d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4989d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4989d-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4989d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4989d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4989d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4989d-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4989d-118">The call timed out.</span></span>|  
|<span data-ttu-id="4989d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4989d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4989d-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4989d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4989d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4989d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4989d-122">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber wartete auf, oder die aktuelle `IHostTask` Instanz ist keiner Aufgabe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4989d-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="4989d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4989d-123">E_FAIL</span></span>|<span data-ttu-id="4989d-124">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4989d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4989d-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4989d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4989d-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4989d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4989d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4989d-127">Requirements</span></span>  
 <span data-ttu-id="4989d-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4989d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4989d-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4989d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4989d-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4989d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4989d-131">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4989d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4989d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4989d-132">See also</span></span>

- [<span data-ttu-id="4989d-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4989d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4989d-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4989d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4989d-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4989d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4989d-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4989d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="4989d-137">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4989d-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
