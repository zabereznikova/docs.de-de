---
title: ICLRDebugManager::SetConnectionTasks-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb4210972ba15a7ba3c7df5981e668cb5542f5c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471406"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="dbcfe-102">ICLRDebugManager::SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="dbcfe-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="dbcfe-103">Ordnet einer Liste von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanzen mit einem Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbcfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbcfe-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbcfe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbcfe-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="dbcfe-106">[in] Der Host-spezifische Bezeichner für die Verbindung mit dem verknüpft die `ppCLRTask` Array.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="dbcfe-107">[in] Die Anzahl der Elemente des `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="dbcfe-108">Diese Zahl muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="dbcfe-109">[in] Ein Array von `ICLRTask` Zeigern, die Verbindung durch identifiziert wird zugeordnet `id`.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="dbcfe-110">Dieses Array muss mindestens einen Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbcfe-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dbcfe-111">Return Value</span></span>  
  
|<span data-ttu-id="dbcfe-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbcfe-112">HRESULT</span></span>|<span data-ttu-id="dbcfe-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbcfe-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbcfe-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbcfe-114">S_OK</span></span>|<span data-ttu-id="dbcfe-115">`SetConnectionTasks` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="dbcfe-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbcfe-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbcfe-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbcfe-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbcfe-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbcfe-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-119">The call timed out.</span></span>|  
|<span data-ttu-id="dbcfe-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbcfe-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbcfe-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbcfe-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbcfe-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbcfe-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbcfe-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbcfe-124">E_FAIL</span></span>|<span data-ttu-id="dbcfe-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbcfe-126">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbcfe-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dbcfe-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dbcfe-128">E_INVALIDARG</span></span>|<span data-ttu-id="dbcfe-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nicht aufgerufen wurde mithilfe dieses Werts von `id`, oder `dwCount` oder `id` ist 0 (null) oder eines der Elemente des `ppCLRTask` ist null.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbcfe-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbcfe-130">Remarks</span></span>  
 <span data-ttu-id="dbcfe-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, `SetConnectionTasks`, und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), zum Aufgabenlisten-IDs und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dbcfe-132">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jede Gruppe von Tasks aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="dbcfe-133">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="dbcfe-134">`SetConnectionTasks` als Nächstes aufgerufen, um Geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="dbcfe-135">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und -ID und Anzeigename zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="dbcfe-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbcfe-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbcfe-136">Requirements</span></span>  
 <span data-ttu-id="dbcfe-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbcfe-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbcfe-138">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbcfe-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbcfe-139">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dbcfe-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbcfe-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbcfe-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcfe-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbcfe-141">See also</span></span>
- [<span data-ttu-id="dbcfe-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbcfe-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="dbcfe-143">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbcfe-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="dbcfe-144">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="dbcfe-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="dbcfe-145">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="dbcfe-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="dbcfe-146">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbcfe-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
