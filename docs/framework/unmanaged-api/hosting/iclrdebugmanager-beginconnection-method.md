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
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133990"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="db237-102">ICLRDebugManager::BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="db237-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="db237-103">Stellt eine neue Verbindung zwischen dem Host und den Debugger, eine Liste der Vorgänge einen Bezeichner und einen benutzerfreundlichen Namen zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="db237-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db237-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db237-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db237-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db237-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="db237-106">[in] Ein Bezeichner, die Liste der common Language Runtime (CLR)-Aufgaben zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="db237-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="db237-107">[in] Ein Anzeigename, der Liste der CLR-Tasks zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="db237-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db237-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db237-108">Return Value</span></span>  
  
|<span data-ttu-id="db237-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db237-109">HRESULT</span></span>|<span data-ttu-id="db237-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db237-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db237-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="db237-111">S_OK</span></span>|`BeginConnection` <span data-ttu-id="db237-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db237-112">returned successfully.</span></span>|  
|<span data-ttu-id="db237-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db237-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db237-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="db237-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db237-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db237-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db237-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db237-116">The call timed out.</span></span>|  
|<span data-ttu-id="db237-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db237-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db237-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="db237-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db237-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db237-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db237-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="db237-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db237-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db237-121">E_FAIL</span></span>|<span data-ttu-id="db237-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db237-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db237-123">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db237-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db237-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="db237-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="db237-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="db237-125">E_INVALIDARG</span></span>|`dwConnectionId` <span data-ttu-id="db237-126">wurde von 0 (null), oder `BeginConnection` aufgerufen wurde bereits mit diesem `dwConnectionId` Wert oder `szConnectionName` war null.</span><span class="sxs-lookup"><span data-stu-id="db237-126">was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="db237-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="db237-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="db237-128">Halten die Liste der Aufgaben im Zusammenhang mit dieser Verbindung konnte nicht genügend Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="db237-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db237-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db237-129">Remarks</span></span>  
 <span data-ttu-id="db237-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), zum Aufgabenlisten-IDs und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="db237-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db237-131">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jede Gruppe von Tasks aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="db237-131">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="db237-132">wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="db237-132">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="db237-133">als Nächstes aufgerufen, um Geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="db237-133">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="db237-134">wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und -ID und Anzeigename zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="db237-134">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db237-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db237-135">Requirements</span></span>  
 <span data-ttu-id="db237-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db237-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db237-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db237-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db237-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db237-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="db237-139">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="db237-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db237-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db237-140">See also</span></span>

- [<span data-ttu-id="db237-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db237-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="db237-142">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db237-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="db237-143">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="db237-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="db237-144">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="db237-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="db237-145">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db237-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
