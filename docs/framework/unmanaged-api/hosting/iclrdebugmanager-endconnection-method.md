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
ms.openlocfilehash: 425f40da7a53aa4af1bd14964a8136add2f59f0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135214"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="bacc3-102">ICLRDebugManager::EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="bacc3-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="bacc3-103">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einem Bezeichner und einem anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="bacc3-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bacc3-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bacc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bacc3-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="bacc3-106">in Der Host spezifische Bezeichner für die Verbindung und die zugeordnete Liste der Common Language Runtime Tasks (CLR).</span><span class="sxs-lookup"><span data-stu-id="bacc3-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bacc3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bacc3-107">Return Value</span></span>  
  
|<span data-ttu-id="bacc3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bacc3-108">HRESULT</span></span>|<span data-ttu-id="bacc3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bacc3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bacc3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bacc3-110">S_OK</span></span>|<span data-ttu-id="bacc3-111">`EndConnection` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bacc3-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="bacc3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bacc3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bacc3-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="bacc3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bacc3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bacc3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bacc3-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="bacc3-115">The call timed out.</span></span>|  
|<span data-ttu-id="bacc3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bacc3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bacc3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bacc3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bacc3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bacc3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bacc3-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="bacc3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bacc3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bacc3-120">E_FAIL</span></span>|<span data-ttu-id="bacc3-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bacc3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bacc3-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bacc3-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bacc3-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bacc3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bacc3-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bacc3-124">E_INVALIDARG</span></span>|<span data-ttu-id="bacc3-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) wurde nie mit `dwConnectionId`aufgerufen, oder `dwConnectionId` war 0 (null).</span><span class="sxs-lookup"><span data-stu-id="bacc3-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bacc3-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bacc3-126">Remarks</span></span>  
 <span data-ttu-id="bacc3-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)und `EndConnection`zum Zuordnen von Aufgabenlisten zu Bezeichnernamen und anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="bacc3-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bacc3-128">Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bacc3-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="bacc3-129">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="bacc3-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="bacc3-130">`SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bacc3-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="bacc3-131">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bacc3-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacc3-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bacc3-132">Requirements</span></span>  
 <span data-ttu-id="bacc3-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bacc3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacc3-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="bacc3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bacc3-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bacc3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bacc3-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacc3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacc3-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bacc3-137">See also</span></span>

- [<span data-ttu-id="bacc3-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacc3-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="bacc3-139">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacc3-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="bacc3-140">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="bacc3-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="bacc3-141">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="bacc3-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="bacc3-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacc3-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
