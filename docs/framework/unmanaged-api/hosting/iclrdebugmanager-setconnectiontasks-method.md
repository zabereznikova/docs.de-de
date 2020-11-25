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
ms.openlocfilehash: 5df01ac929874d00a5fddda83f532927dc46d67b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719839"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="62005-102">ICLRDebugManager::SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="62005-102">ICLRDebugManager::SetConnectionTasks Method</span></span>

<span data-ttu-id="62005-103">Ordnet eine Liste von [ICLRTask](iclrtask-interface.md) -Instanzen einem Bezeichner und einem anzeigen Amen zu.</span><span class="sxs-lookup"><span data-stu-id="62005-103">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62005-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62005-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62005-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62005-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="62005-106">in Der Host spezifische Bezeichner für die Verbindung, der das Array zugeordnet werden soll `ppCLRTask` .</span><span class="sxs-lookup"><span data-stu-id="62005-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="62005-107">in Die Anzahl der Member von `ppCLRTask` .</span><span class="sxs-lookup"><span data-stu-id="62005-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="62005-108">Diese Zahl muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="62005-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="62005-109">in Ein Array von `ICLRTask` Zeigern, die der durch identifizierten Verbindung zugeordnet werden sollen `id` .</span><span class="sxs-lookup"><span data-stu-id="62005-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="62005-110">Dieses Array muss mindestens einen Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="62005-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62005-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62005-111">Return Value</span></span>  
  
|<span data-ttu-id="62005-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62005-112">HRESULT</span></span>|<span data-ttu-id="62005-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62005-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62005-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="62005-114">S_OK</span></span>|<span data-ttu-id="62005-115">`SetConnectionTasks` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62005-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="62005-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62005-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62005-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="62005-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62005-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62005-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62005-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="62005-119">The call timed out.</span></span>|  
|<span data-ttu-id="62005-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62005-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62005-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="62005-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62005-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62005-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62005-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="62005-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62005-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62005-124">E_FAIL</span></span>|<span data-ttu-id="62005-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62005-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62005-126">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62005-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62005-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="62005-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="62005-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="62005-128">E_INVALIDARG</span></span>|<span data-ttu-id="62005-129">[BeginConnection](iclrdebugmanager-beginconnection-method.md) wurde nicht mit diesem Wert von aufgerufen `id` , oder, `dwCount` oder `id` ist 0 (null), oder eines der Elemente von `ppCLRTask` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="62005-129">[BeginConnection](iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62005-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62005-130">Remarks</span></span>  

 <span data-ttu-id="62005-131">[ICLRDebugManager](iclrdebugmanager-interface.md) bietet drei Methoden, `BeginConnection` , `SetConnectionTasks` und [EndConnection](iclrdebugmanager-endconnection-method.md), um Aufgabenlisten mit Bezeichnerzeichen und anzeigen Amen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="62005-131">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="62005-132">Diese drei Methoden müssen für jeden Satz von Aufgaben in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62005-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="62005-133">`BeginConnection` wird zuerst aufgerufen, um eine neue Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="62005-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="62005-134">`SetConnectionTasks` wird als nächstes aufgerufen, um die Gruppe von Aufgaben bereitzustellen, die dieser Verbindung zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62005-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="62005-135">`EndConnection` wird zuletzt aufgerufen, um die Zuordnung zwischen der Aufgabenliste und dem Bezeichner und dem anzeigen Amen zu entfernen. Allerdings können Aufrufe für verschiedene Verbindungen in eine andere Liste eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="62005-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62005-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="62005-136">Requirements</span></span>  

 <span data-ttu-id="62005-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62005-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62005-138">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="62005-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62005-139">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="62005-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62005-140">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62005-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62005-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62005-141">See also</span></span>

- [<span data-ttu-id="62005-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62005-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="62005-143">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62005-143">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="62005-144">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="62005-144">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="62005-145">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="62005-145">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="62005-146">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62005-146">IHostControl Interface</span></span>](ihostcontrol-interface.md)
