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
ms.openlocfilehash: ccc08ae210dd02bc71a1d83bc81525a7308c20e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770385"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="8af83-102">ICLRTask::SwitchIn-Methode</span><span class="sxs-lookup"><span data-stu-id="8af83-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="8af83-103">Informiert die common Language Runtime (CLR), die die Aufgabe, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz stellt ist jetzt in einen betriebsfähigen Zustand wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8af83-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8af83-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8af83-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8af83-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="8af83-106">[in] Ein Handle für den physischen Thread, der auf dem die Aufgabe, die von der aktuellen dargestellt `ICLRTask` Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8af83-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8af83-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8af83-107">Return Value</span></span>  
  
|<span data-ttu-id="8af83-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8af83-108">HRESULT</span></span>|<span data-ttu-id="8af83-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8af83-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8af83-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8af83-110">S_OK</span></span>|<span data-ttu-id="8af83-111">`SwitchIn` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8af83-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="8af83-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8af83-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8af83-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8af83-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8af83-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8af83-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8af83-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8af83-115">The call timed out.</span></span>|  
|<span data-ttu-id="8af83-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af83-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8af83-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8af83-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8af83-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8af83-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8af83-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8af83-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8af83-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8af83-120">E_FAIL</span></span>|<span data-ttu-id="8af83-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8af83-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8af83-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8af83-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8af83-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8af83-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8af83-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8af83-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8af83-125">`SwitchIn` wurde aufgerufen, ohne einen früheren Aufruf von [SwitchOut-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="8af83-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af83-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8af83-126">Remarks</span></span>  
 <span data-ttu-id="8af83-127">Die `threadHandle` Parameter gibt ein Handle für den auf dem die Aufgabe, von der aktuellen dargestellt Betriebssystemthread `ICLRTask` Instanz wurde geplant.</span><span class="sxs-lookup"><span data-stu-id="8af83-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="8af83-128">Wenn der Identitätswechsel auf diesem Thread aufgetreten ist, müssen Sie aufrufen [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) vor dem Wechseln in der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="8af83-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8af83-129">Ein Aufruf von `SwitchIn` ohne einen früheren Aufruf von `SwitchOut` HRESULT-Fehlerwert HOST_E_INVALIDOPERATION schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="8af83-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af83-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8af83-130">Requirements</span></span>  
 <span data-ttu-id="8af83-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af83-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af83-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8af83-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af83-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8af83-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af83-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af83-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af83-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8af83-135">See also</span></span>

- [<span data-ttu-id="8af83-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8af83-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8af83-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8af83-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8af83-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8af83-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8af83-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8af83-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
