---
title: ICLRDebugManager::EndConnection-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60e110e019619f9336b240fdc5aee8fa66c5bcdb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479183"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="8c000-102">ICLRDebugManager::EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="8c000-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="8c000-103">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="8c000-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c000-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c000-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c000-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c000-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="8c000-106">[in] Der Host-spezifischen Bezeichner für die Verbindung und der Liste der common Language Runtime (CLR)-Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="8c000-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c000-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8c000-107">Return Value</span></span>  
  
|<span data-ttu-id="8c000-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c000-108">HRESULT</span></span>|<span data-ttu-id="8c000-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c000-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c000-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c000-110">S_OK</span></span>|<span data-ttu-id="8c000-111">`EndConnection` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c000-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="8c000-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c000-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c000-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c000-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c000-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c000-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c000-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8c000-115">The call timed out.</span></span>|  
|<span data-ttu-id="8c000-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c000-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c000-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8c000-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c000-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c000-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c000-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8c000-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c000-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c000-120">E_FAIL</span></span>|<span data-ttu-id="8c000-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8c000-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c000-122">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c000-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c000-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8c000-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8c000-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8c000-124">E_INVALIDARG</span></span>|<span data-ttu-id="8c000-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) wurde nie aufgerufen mit `dwConnectionId`, oder `dwConnectionId` wurde von 0 (null).</span><span class="sxs-lookup"><span data-stu-id="8c000-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c000-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c000-126">Remarks</span></span>  
 <span data-ttu-id="8c000-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und `EndConnection`, zum Aufgabenlisten-IDs und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8c000-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c000-128">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jede Gruppe von Tasks aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8c000-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="8c000-129">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c000-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="8c000-130">`SetConnectionTasks` als Nächstes aufgerufen, um Geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c000-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="8c000-131">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und -ID und Anzeigename zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="8c000-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c000-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c000-132">Requirements</span></span>  
 <span data-ttu-id="8c000-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c000-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c000-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8c000-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c000-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8c000-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c000-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c000-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c000-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c000-137">See also</span></span>
- [<span data-ttu-id="8c000-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c000-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8c000-139">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c000-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="8c000-140">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="8c000-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="8c000-141">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="8c000-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="8c000-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c000-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
