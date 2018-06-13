---
title: ICLRDebugManager::BeginConnection-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1a285fca381195191def7612aef41c4bf72f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435510"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="3bdcd-102">ICLRDebugManager::BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="3bdcd-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="3bdcd-103">Wird eine neue Verbindung zwischen dem Host und den Debugger, um eine Liste der Aufgaben eines Bezeichners und einen Anzeigenamen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bdcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bdcd-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bdcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3bdcd-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="3bdcd-106">[in] Ein Bezeichner, der Liste der common Language Runtime (CLR)-Aufgaben zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="3bdcd-107">[in] Ein Anzeigename, der Liste der CLR-Aufgaben zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bdcd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3bdcd-108">Return Value</span></span>  
  
|<span data-ttu-id="3bdcd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bdcd-109">HRESULT</span></span>|<span data-ttu-id="3bdcd-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bdcd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bdcd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bdcd-111">S_OK</span></span>|<span data-ttu-id="3bdcd-112">`BeginConnection` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="3bdcd-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3bdcd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bdcd-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bdcd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bdcd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bdcd-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-116">The call timed out.</span></span>|  
|<span data-ttu-id="3bdcd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bdcd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bdcd-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bdcd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bdcd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bdcd-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bdcd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bdcd-121">E_FAIL</span></span>|<span data-ttu-id="3bdcd-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bdcd-123">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bdcd-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3bdcd-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3bdcd-125">E_INVALIDARG</span></span>|<span data-ttu-id="3bdcd-126">`dwConnectionId` wurde von 0 (null), oder `BeginConnection` verwenden Sie diese Funktion wurde bereits aufgerufen `dwConnectionId` Wert oder `szConnectionName` war null.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="3bdcd-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3bdcd-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3bdcd-128">Halten Sie die Liste der Aufgaben im Zusammenhang mit dieser Verbindung konnte nicht genügend Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bdcd-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bdcd-129">Remarks</span></span>  
 <span data-ttu-id="3bdcd-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), für das Aufgabenlisten mit Bezeichnern und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3bdcd-131">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jeden Satz von Aufgaben aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="3bdcd-132">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="3bdcd-133">`SetConnectionTasks` wird als Nächstes geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="3bdcd-134">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und Bezeichner und Anzeigenamen zu entfernen. Allerdings können Aufrufe für unterschiedliche Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="3bdcd-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bdcd-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bdcd-135">Requirements</span></span>  
 <span data-ttu-id="3bdcd-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bdcd-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bdcd-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3bdcd-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bdcd-138">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3bdcd-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bdcd-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bdcd-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bdcd-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bdcd-140">See Also</span></span>  
 [<span data-ttu-id="3bdcd-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bdcd-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3bdcd-142">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bdcd-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="3bdcd-143">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="3bdcd-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="3bdcd-144">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="3bdcd-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="3bdcd-145">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bdcd-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
