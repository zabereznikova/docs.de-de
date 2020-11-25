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
ms.openlocfilehash: d6f22d6185f4063078463043a6ffd46e56289267
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719852"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="adcf6-102">ICLRDebugManager::EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="adcf6-102">ICLRDebugManager::EndConnection Method</span></span>

<span data-ttu-id="adcf6-103">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einem Bezeichner und einem anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="adcf6-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcf6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="adcf6-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adcf6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="adcf6-105">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="adcf6-106">in Der Host spezifische Bezeichner für die Verbindung und die zugeordnete Liste der Common Language Runtime Tasks (CLR).</span><span class="sxs-lookup"><span data-stu-id="adcf6-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adcf6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="adcf6-107">Return Value</span></span>  
  
|<span data-ttu-id="adcf6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adcf6-108">HRESULT</span></span>|<span data-ttu-id="adcf6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="adcf6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adcf6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="adcf6-110">S_OK</span></span>|<span data-ttu-id="adcf6-111">`EndConnection` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="adcf6-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="adcf6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adcf6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adcf6-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="adcf6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adcf6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adcf6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adcf6-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="adcf6-115">The call timed out.</span></span>|  
|<span data-ttu-id="adcf6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adcf6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adcf6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="adcf6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adcf6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adcf6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adcf6-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="adcf6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adcf6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adcf6-120">E_FAIL</span></span>|<span data-ttu-id="adcf6-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="adcf6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adcf6-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adcf6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adcf6-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="adcf6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="adcf6-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="adcf6-124">E_INVALIDARG</span></span>|<span data-ttu-id="adcf6-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) wurde nie mit aufgerufen `dwConnectionId` , oder `dwConnectionId` war 0 (null).</span><span class="sxs-lookup"><span data-stu-id="adcf6-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adcf6-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="adcf6-126">Remarks</span></span>  

 <span data-ttu-id="adcf6-127">[ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)und `EndConnection` , um Aufgabenlisten mit bezeichnerwerten und anzeigen Amen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="adcf6-127">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adcf6-128">Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="adcf6-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="adcf6-129">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="adcf6-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="adcf6-130">`SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="adcf6-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="adcf6-131">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="adcf6-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adcf6-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="adcf6-132">Requirements</span></span>  

 <span data-ttu-id="adcf6-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adcf6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adcf6-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="adcf6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adcf6-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="adcf6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adcf6-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adcf6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcf6-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="adcf6-137">See also</span></span>

- [<span data-ttu-id="adcf6-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adcf6-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="adcf6-139">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adcf6-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="adcf6-140">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="adcf6-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="adcf6-141">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="adcf6-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="adcf6-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adcf6-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
