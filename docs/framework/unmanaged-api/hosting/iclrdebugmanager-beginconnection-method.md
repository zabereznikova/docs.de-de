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
ms.openlocfilehash: c5b41e4209141c0396ec8a1da766b80043be8807
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726157"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="08f1f-102">ICLRDebugManager::BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="08f1f-102">ICLRDebugManager::BeginConnection Method</span></span>

<span data-ttu-id="08f1f-103">Stellt eine neue Verbindung zwischen dem Host und dem Debugger her, um eine Liste mit Aufgaben einem Bezeichner und einem anzeigen Amen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="08f1f-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08f1f-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f1f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08f1f-105">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="08f1f-106">in Ein Bezeichner, der der Liste der Common Language Runtime (CLR)-Tasks zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08f1f-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="08f1f-107">in Ein Anzeige Name, der der Liste der CLR-Tasks zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08f1f-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f1f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08f1f-108">Return Value</span></span>  
  
|<span data-ttu-id="08f1f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08f1f-109">HRESULT</span></span>|<span data-ttu-id="08f1f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="08f1f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08f1f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="08f1f-111">S_OK</span></span>|<span data-ttu-id="08f1f-112">`BeginConnection` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08f1f-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="08f1f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08f1f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08f1f-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="08f1f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08f1f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08f1f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08f1f-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="08f1f-116">The call timed out.</span></span>|  
|<span data-ttu-id="08f1f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08f1f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08f1f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="08f1f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08f1f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08f1f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08f1f-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="08f1f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08f1f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08f1f-121">E_FAIL</span></span>|<span data-ttu-id="08f1f-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08f1f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08f1f-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08f1f-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08f1f-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="08f1f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08f1f-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="08f1f-125">E_INVALIDARG</span></span>|<span data-ttu-id="08f1f-126">`dwConnectionId` war NULL, oder `BeginConnection` wurde bereits mit diesem `dwConnectionId` Wert aufgerufen, oder `szConnectionName` war NULL.</span><span class="sxs-lookup"><span data-stu-id="08f1f-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="08f1f-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="08f1f-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="08f1f-128">Es konnte nicht genügend Arbeitsspeicher zugeordnet werden, um die Liste der Aufgaben zu speichern, die dieser Verbindung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="08f1f-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08f1f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08f1f-129">Remarks</span></span>  

 <span data-ttu-id="08f1f-130">[ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)und [EndConnection](iclrdebugmanager-endconnection-method.md), um Aufgabenlisten mit bezeichnerwerten und anzeigen Amen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="08f1f-130">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="08f1f-131">Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="08f1f-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="08f1f-132">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="08f1f-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="08f1f-133">`SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08f1f-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="08f1f-134">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="08f1f-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f1f-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08f1f-135">Requirements</span></span>  

 <span data-ttu-id="08f1f-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f1f-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f1f-137">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="08f1f-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08f1f-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08f1f-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08f1f-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f1f-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f1f-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08f1f-140">See also</span></span>

- [<span data-ttu-id="08f1f-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f1f-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="08f1f-142">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f1f-142">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="08f1f-143">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="08f1f-143">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="08f1f-144">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="08f1f-144">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="08f1f-145">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f1f-145">IHostControl Interface</span></span>](ihostcontrol-interface.md)
