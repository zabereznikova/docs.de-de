---
title: ICLRTask::SwitchIn-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchIn
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01e91c4febfebf8ec8ffd4c0ffbf8e33a4ff0edd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="1c151-102">ICLRTask::SwitchIn-Methode</span><span class="sxs-lookup"><span data-stu-id="1c151-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="1c151-103">Benachrichtigt die common Language Runtime (CLR), die die Aufgabe, die das aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz stellt befindet sich nun im betriebsbereiten Zustand.</span><span class="sxs-lookup"><span data-stu-id="1c151-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c151-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c151-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c151-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c151-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="1c151-106">[in] Ein Handle für den physischen Thread auf dem die Aufgabe, von der aktuellen dargestellt `ICLRTask` Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c151-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c151-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c151-107">Return Value</span></span>  
  
|<span data-ttu-id="1c151-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c151-108">HRESULT</span></span>|<span data-ttu-id="1c151-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c151-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c151-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c151-110">S_OK</span></span>|<span data-ttu-id="1c151-111">`SwitchIn`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1c151-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="1c151-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="1c151-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c151-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1c151-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c151-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c151-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c151-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1c151-115">The call timed out.</span></span>|  
|<span data-ttu-id="1c151-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c151-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c151-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1c151-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c151-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c151-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c151-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1c151-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c151-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c151-120">E_FAIL</span></span>|<span data-ttu-id="1c151-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1c151-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c151-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1c151-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c151-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1c151-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1c151-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1c151-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1c151-125">`SwitchIn`wurde aufgerufen, ohne einen früheren Aufruf [SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="1c151-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c151-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c151-126">Remarks</span></span>  
 <span data-ttu-id="1c151-127">Die `threadHandle` Parameter stellt ein Handle an den Betriebssystem-Thread auf dem die Aufgabe, von der aktuellen dargestellt `ICLRTask` Instanz wurde geplant.</span><span class="sxs-lookup"><span data-stu-id="1c151-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="1c151-128">Wenn Identitätswechsel in diesem Thread aufgetreten ist, müssen Sie aufrufen [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) vor dem Wechseln in der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="1c151-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c151-129">Ein Aufruf von `SwitchIn` ohne einen früheren Aufruf `SwitchOut` HRESULT-Fehlerwert HOST_E_INVALIDOPERATION fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="1c151-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c151-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c151-130">Requirements</span></span>  
 <span data-ttu-id="1c151-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c151-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c151-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c151-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c151-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1c151-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c151-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c151-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c151-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c151-135">See Also</span></span>  
 [<span data-ttu-id="1c151-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c151-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1c151-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c151-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1c151-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c151-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1c151-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c151-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
