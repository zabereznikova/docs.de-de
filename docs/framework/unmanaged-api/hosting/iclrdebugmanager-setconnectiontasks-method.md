---
title: ICLRDebugManager::SetConnectionTasks-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetConnectionTasks
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 354e876bf69a82bf1eb0ed3907a03e4b94d60f19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="df288-102">ICLRDebugManager::SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="df288-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="df288-103">Ordnet eine Liste der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanzen einen Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="df288-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df288-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df288-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df288-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df288-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="df288-106">[in] Der Host-spezifische Bezeichner für die Verbindung mit dem verknüpft die `ppCLRTask` Array.</span><span class="sxs-lookup"><span data-stu-id="df288-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="df288-107">[in] Die Anzahl der Elemente des `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="df288-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="df288-108">Diese Zahl muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="df288-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="df288-109">[in] Ein Array von `ICLRTask` Zeigern, die Verbindung mit dem identifizierten zugeordnet `id`.</span><span class="sxs-lookup"><span data-stu-id="df288-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="df288-110">Dieses Array muss mindestens ein Mitglied enthalten.</span><span class="sxs-lookup"><span data-stu-id="df288-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df288-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df288-111">Return Value</span></span>  
  
|<span data-ttu-id="df288-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df288-112">HRESULT</span></span>|<span data-ttu-id="df288-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df288-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df288-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="df288-114">S_OK</span></span>|<span data-ttu-id="df288-115">`SetConnectionTasks`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="df288-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="df288-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="df288-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df288-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="df288-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df288-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df288-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df288-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="df288-119">The call timed out.</span></span>|  
|<span data-ttu-id="df288-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df288-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df288-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="df288-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df288-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df288-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df288-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="df288-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df288-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df288-124">E_FAIL</span></span>|<span data-ttu-id="df288-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="df288-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df288-126">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="df288-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df288-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="df288-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="df288-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="df288-128">E_INVALIDARG</span></span>|<span data-ttu-id="df288-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nicht aufgerufen wurde mithilfe dieses Werts von `id`, oder `dwCount` oder `id` ist 0 (null) oder eines der Elemente des `ppCLRTask` ist null.</span><span class="sxs-lookup"><span data-stu-id="df288-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df288-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df288-130">Remarks</span></span>  
 <span data-ttu-id="df288-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, `SetConnectionTasks`, und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), für das Aufgabenlisten mit Bezeichnern und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="df288-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="df288-132">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jeden Satz von Aufgaben aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="df288-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="df288-133">`BeginConnection`wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="df288-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="df288-134">`SetConnectionTasks`wird als Nächstes geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="df288-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="df288-135">`EndConnection`wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und Bezeichner und Anzeigenamen zu entfernen. Allerdings können Aufrufe für unterschiedliche Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="df288-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df288-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df288-136">Requirements</span></span>  
 <span data-ttu-id="df288-137">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df288-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df288-138">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df288-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df288-139">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df288-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df288-140">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df288-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df288-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df288-141">See Also</span></span>  
 [<span data-ttu-id="df288-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df288-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="df288-143">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df288-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="df288-144">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="df288-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="df288-145">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="df288-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="df288-146">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df288-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
