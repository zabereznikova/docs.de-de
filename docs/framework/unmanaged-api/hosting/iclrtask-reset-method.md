---
title: ICLRTask::Reset-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae0a2a3af532b81d7b346cdd17da1712dfa3cba8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499926"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="54709-102">ICLRTask::Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="54709-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="54709-103">Informiert der common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit einer anderen Aufgabe darstellen.</span><span class="sxs-lookup"><span data-stu-id="54709-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54709-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54709-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54709-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="54709-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="54709-106">[in] `true`, wenn die Common Language Runtime alle threadbezogene statische Werte zusätzlich zu den Sicherheits- und Gebietsschema-Informationen im Zusammenhang mit der aktuellen zurücksetzen sollten `ICLRTask` -Instanz ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="54709-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="54709-107">Wenn der Wert ist `true`, die Laufzeit setzt mithilfe von gespeicherten Daten, <xref:System.Threading.Thread.AllocateDataSlot%2A> oder <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span><span class="sxs-lookup"><span data-stu-id="54709-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54709-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54709-108">Return Value</span></span>  
  
|<span data-ttu-id="54709-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54709-109">HRESULT</span></span>|<span data-ttu-id="54709-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54709-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54709-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="54709-111">S_OK</span></span>|<span data-ttu-id="54709-112">`Reset` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="54709-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="54709-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54709-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54709-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="54709-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="54709-115">erfolgreich</span><span class="sxs-lookup"><span data-stu-id="54709-115">successfully</span></span>|  
|<span data-ttu-id="54709-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54709-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54709-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="54709-117">The call timed out.</span></span>|  
|<span data-ttu-id="54709-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54709-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54709-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="54709-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54709-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54709-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54709-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="54709-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54709-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54709-122">E_FAIL</span></span>|<span data-ttu-id="54709-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="54709-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54709-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54709-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54709-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="54709-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54709-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54709-126">Remarks</span></span>  
 <span data-ttu-id="54709-127">Die CLR kann wiederverwenden, die zuvor erstellte `ICLRTask` Instanzen, um zu vermeiden, dass neue Instanzen erstellt werden jedes Mal, wenn es sich um eine neue Aufgabe benötigt.</span><span class="sxs-lookup"><span data-stu-id="54709-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="54709-128">Der Host kann mithilfe dieser Funktion durch den Aufruf `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) Wenn es eine Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="54709-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="54709-129">Die folgende Liste enthält die normalen Lebenszyklus einer `ICLRTask` Instanz:</span><span class="sxs-lookup"><span data-stu-id="54709-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="54709-130">Die Common Language Runtime erstellt ein neues `ICLRTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="54709-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="54709-131">Ruft die Laufzeit [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) Abrufen eines Verweises auf die aktuelle Hostaufgabe.</span><span class="sxs-lookup"><span data-stu-id="54709-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="54709-132">Ruft die Laufzeit [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) , die Hostaufgabe die neue Instanz zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="54709-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="54709-133">Der Task wird ausgeführt und abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="54709-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="54709-134">Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="54709-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="54709-135">`Reset` ändert dieses Szenario gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="54709-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="54709-136">In Schritt 5 oben der Host ruft `Reset` auf die Aufgabe in einem fehlerfreien Status zurückzusetzen und dann die `ICLRTask` Instanz zugeordneten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="54709-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="54709-137">Falls gewünscht, kann auch der Host Zwischenspeichern der `IHostTask` Instanz zur Wiederverwendung.</span><span class="sxs-lookup"><span data-stu-id="54709-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="54709-138">Klicken Sie in Schritt 1 oben, die Runtime eine wiederverwendete `ICLRTask` aus dem Zwischenspeicher, anstatt eine neue Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="54709-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="54709-139">Dieser Ansatz funktioniert gut, wenn der Host auch einen Pool von wiederverwendbaren arbeitstasks hat.</span><span class="sxs-lookup"><span data-stu-id="54709-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="54709-140">Wenn der Host zerstört eines seiner `IHostTask` -Instanzen, zerstört er die entsprechende `ICLRTask` durch Aufrufen von `ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="54709-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54709-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54709-141">Requirements</span></span>  
 <span data-ttu-id="54709-142">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54709-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54709-143">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54709-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54709-144">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="54709-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54709-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54709-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54709-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54709-146">See also</span></span>
- [<span data-ttu-id="54709-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54709-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="54709-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54709-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="54709-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54709-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="54709-150">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54709-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
