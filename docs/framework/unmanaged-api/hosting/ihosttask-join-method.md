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
ms.openlocfilehash: dda68041dbf4efa82a35c48702d83aa231462fef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121372"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="f5a5a-102">IHostTask::Join-Methode</span><span class="sxs-lookup"><span data-stu-id="f5a5a-102">IHostTask::Join Method</span></span>
<span data-ttu-id="f5a5a-103">Blockiert die aufrufende Aufgabe, bis die durch die aktuelle [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellte Aufgabe abgeschlossen ist, das angegebene Zeitintervall abgelaufen ist oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5a5a-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="f5a5a-106">in Das Zeitintervall (in Millisekunden), das gewartet werden soll, bis die Aufgabe beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="f5a5a-107">Wenn dieses Intervall abläuft, bevor der Task beendet wird, wird die Blockierung der aufrufenden Aufgabe aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="f5a5a-108">in Einer der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="f5a5a-109">Der Wert WAIT_ALERTABLE weist den Host an, die Aufgabe zu aktivieren, wenn `Alert` vor `milliseconds` verstrichen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a5a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5a5a-110">Return Value</span></span>  
  
|<span data-ttu-id="f5a5a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5a5a-111">HRESULT</span></span>|<span data-ttu-id="f5a5a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5a5a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5a5a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5a5a-113">S_OK</span></span>|<span data-ttu-id="f5a5a-114">`Join` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="f5a5a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5a5a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5a5a-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5a5a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5a5a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5a5a-118">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-118">The call timed out.</span></span>|  
|<span data-ttu-id="f5a5a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5a5a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5a5a-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5a5a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5a5a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5a5a-122">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf gewartet hat, oder die aktuelle `IHostTask` Instanz ist keiner Aufgabe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="f5a5a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5a5a-123">E_FAIL</span></span>|<span data-ttu-id="f5a5a-124">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5a5a-125">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5a5a-126">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f5a5a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5a5a-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5a5a-127">Requirements</span></span>  
 <span data-ttu-id="f5a5a-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a5a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a5a-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f5a5a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5a5a-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5a5a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5a5a-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a5a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a5a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5a5a-132">See also</span></span>

- [<span data-ttu-id="f5a5a-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a5a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f5a5a-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a5a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f5a5a-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a5a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f5a5a-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a5a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f5a5a-137">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f5a5a-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
