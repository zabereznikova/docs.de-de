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
ms.openlocfilehash: c58ce0389c77b6534cbbf37fe985f89c187065df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435824"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="d3c55-102">ICLRDebugManager::EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="d3c55-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="d3c55-103">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="d3c55-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3c55-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3c55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3c55-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="d3c55-106">[in] Der Host-spezifische Bezeichner für die Verbindung und der zugehörigen Liste der common Language Runtime (CLR)-Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="d3c55-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3c55-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3c55-107">Return Value</span></span>  
  
|<span data-ttu-id="d3c55-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3c55-108">HRESULT</span></span>|<span data-ttu-id="d3c55-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3c55-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3c55-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3c55-110">S_OK</span></span>|<span data-ttu-id="d3c55-111">`EndConnection` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3c55-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="d3c55-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d3c55-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3c55-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c55-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3c55-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3c55-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3c55-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d3c55-115">The call timed out.</span></span>|  
|<span data-ttu-id="d3c55-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3c55-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3c55-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d3c55-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3c55-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3c55-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3c55-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d3c55-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3c55-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3c55-120">E_FAIL</span></span>|<span data-ttu-id="d3c55-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d3c55-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3c55-122">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d3c55-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3c55-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d3c55-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3c55-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d3c55-124">E_INVALIDARG</span></span>|<span data-ttu-id="d3c55-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) hieß nie mit `dwConnectionId`, oder `dwConnectionId` war NULL.</span><span class="sxs-lookup"><span data-stu-id="d3c55-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3c55-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3c55-126">Remarks</span></span>  
 <span data-ttu-id="d3c55-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), und `EndConnection`, für das Aufgabenlisten mit Bezeichnern und Anzeigenamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d3c55-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3c55-128">Diese drei Methoden müssen in einer bestimmten Reihenfolge für jeden Satz von Aufgaben aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d3c55-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="d3c55-129">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d3c55-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="d3c55-130">`SetConnectionTasks` wird als Nächstes geben Sie den Satz von Aufgaben mit dieser Verbindung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3c55-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="d3c55-131">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und Bezeichner und Anzeigenamen zu entfernen. Allerdings können Aufrufe für unterschiedliche Verbindungen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="d3c55-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3c55-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3c55-132">Requirements</span></span>  
 <span data-ttu-id="d3c55-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3c55-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c55-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3c55-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3c55-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d3c55-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3c55-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c55-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c55-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3c55-137">See Also</span></span>  
 [<span data-ttu-id="d3c55-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3c55-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d3c55-139">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3c55-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="d3c55-140">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="d3c55-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="d3c55-141">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="d3c55-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="d3c55-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3c55-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
