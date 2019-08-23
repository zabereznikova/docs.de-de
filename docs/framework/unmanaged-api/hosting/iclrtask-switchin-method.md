---
title: ICLRTask::SwitchIn-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938372"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="6b713-102">ICLRTask::SwitchIn-Methode</span><span class="sxs-lookup"><span data-stu-id="6b713-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="6b713-103">Benachrichtigt den Common Language Runtime (CLR), dass die Aufgabe, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt, jetzt in einem eines ausführbaren-Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="6b713-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b713-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b713-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b713-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b713-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="6b713-106">in Ein Handle für den physischen Thread, in dem die von der aktuellen `ICLRTask` Instanz dargestellte Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6b713-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b713-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b713-107">Return Value</span></span>  
  
|<span data-ttu-id="6b713-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b713-108">HRESULT</span></span>|<span data-ttu-id="6b713-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b713-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b713-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b713-110">S_OK</span></span>|<span data-ttu-id="6b713-111">`SwitchIn`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b713-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="6b713-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b713-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b713-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6b713-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b713-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b713-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b713-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="6b713-115">The call timed out.</span></span>|  
|<span data-ttu-id="6b713-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b713-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b713-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6b713-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b713-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b713-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b713-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="6b713-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b713-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b713-120">E_FAIL</span></span>|<span data-ttu-id="6b713-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6b713-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b713-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b713-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b713-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6b713-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6b713-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="6b713-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="6b713-125">`SwitchIn`wurde aufgerufen, ohne dass ein früherer Aufruf der [SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="6b713-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b713-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b713-126">Remarks</span></span>  
 <span data-ttu-id="6b713-127">Der `threadHandle` -Parameter stellt ein Handle für den Betriebssystem Thread dar, auf dem der von der `ICLRTask` aktuellen Instanz dargestellte Task geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="6b713-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="6b713-128">Wenn in diesem Thread ein Identitätswechsel aufgetreten ist, müssen Sie [IHostSecurityManager:: revertdeself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) vor dem Umschalten in der Aufgabe anrufen.</span><span class="sxs-lookup"><span data-stu-id="6b713-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b713-129">Ein-Rückruf `SwitchIn` ohne einen früheren- `SwitchOut` Rückruf schlägt mit einem HRESULT-Wert von HOST_E_INVALIDOPERATION fehl.</span><span class="sxs-lookup"><span data-stu-id="6b713-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b713-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b713-130">Requirements</span></span>  
 <span data-ttu-id="6b713-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b713-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b713-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b713-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b713-133">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6b713-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b713-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b713-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b713-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b713-135">See also</span></span>

- [<span data-ttu-id="6b713-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b713-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6b713-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b713-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6b713-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b713-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6b713-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b713-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
