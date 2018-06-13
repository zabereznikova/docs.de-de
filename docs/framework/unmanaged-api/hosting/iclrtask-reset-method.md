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
ms.openlocfilehash: 29267d032f5e38e352592edc50dbded68aaa9f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435941"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="65cf2-102">ICLRTask::Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="65cf2-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="65cf2-103">Informiert der common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht es der CLR, die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit einer anderen Aufgabe darstellen.</span><span class="sxs-lookup"><span data-stu-id="65cf2-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65cf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65cf2-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65cf2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65cf2-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="65cf2-106">[in] `true`, wenn die Common Language Runtime alle threadbezogene statische Werte zusätzlich zu den Sicherheits- und Gebietsschema-Informationen im Zusammenhang mit der aktuellen zurücksetzen sollten `ICLRTask` -Instanz hingegen `false`.</span><span class="sxs-lookup"><span data-stu-id="65cf2-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="65cf2-107">Wenn der Wert `true`, die Common Language Runtime setzt mithilfe von gespeicherten Daten, <xref:System.Threading.Thread.AllocateDataSlot%2A> oder <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span><span class="sxs-lookup"><span data-stu-id="65cf2-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65cf2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="65cf2-108">Return Value</span></span>  
  
|<span data-ttu-id="65cf2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65cf2-109">HRESULT</span></span>|<span data-ttu-id="65cf2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65cf2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65cf2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="65cf2-111">S_OK</span></span>|<span data-ttu-id="65cf2-112">`Reset` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65cf2-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="65cf2-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="65cf2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65cf2-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="65cf2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="65cf2-115">erfolgreich</span><span class="sxs-lookup"><span data-stu-id="65cf2-115">successfully</span></span>|  
|<span data-ttu-id="65cf2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65cf2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65cf2-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="65cf2-117">The call timed out.</span></span>|  
|<span data-ttu-id="65cf2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65cf2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65cf2-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="65cf2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65cf2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65cf2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65cf2-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="65cf2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65cf2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65cf2-122">E_FAIL</span></span>|<span data-ttu-id="65cf2-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="65cf2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65cf2-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="65cf2-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65cf2-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="65cf2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65cf2-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65cf2-126">Remarks</span></span>  
 <span data-ttu-id="65cf2-127">Die CLR kann zuvor erstellte wiederverwenden `ICLRTask` Instanzen, um zu vermeiden, dass neue Instanzen erstellt werden jedes Mal, wenn sie eine neue Aufgabe benötigt.</span><span class="sxs-lookup"><span data-stu-id="65cf2-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="65cf2-128">Der Host kann mithilfe dieser Funktion durch Aufrufen von `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) Nachdem sie eine Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="65cf2-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="65cf2-129">Die folgende Liste fasst die normalen Lebenszyklus einer `ICLRTask` Instanz:</span><span class="sxs-lookup"><span data-stu-id="65cf2-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="65cf2-130">Die Common Language Runtime erstellt ein neues `ICLRTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="65cf2-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="65cf2-131">Ruft die Laufzeit [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) Abrufen eines Verweises auf die aktuelle Hostaufgabe.</span><span class="sxs-lookup"><span data-stu-id="65cf2-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="65cf2-132">Ruft die Laufzeit [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) die neue Instanz mit dem Host zuordnen.</span><span class="sxs-lookup"><span data-stu-id="65cf2-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="65cf2-133">Die Aufgabe wird ausgeführt und abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="65cf2-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="65cf2-134">Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="65cf2-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="65cf2-135">`Reset` ändert dieses Szenario auf zwei Arten.</span><span class="sxs-lookup"><span data-stu-id="65cf2-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="65cf2-136">In Schritt 5, der Host ruft `Reset` den Task auf einen fehlerfreien Zustand zurücksetzen, und klicken Sie dann entkoppelt die `ICLRTask` Instanz aus der zugeordneten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="65cf2-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="65cf2-137">Falls gewünscht, kann auch der Host Zwischenspeichern der `IHostTask` Instanz zur Wiederverwendung.</span><span class="sxs-lookup"><span data-stu-id="65cf2-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="65cf2-138">Klicken Sie in Schritt 1 oben, die Runtime eine wiederverwendete `ICLRTask` aus dem Cache, anstatt eine neue Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="65cf2-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="65cf2-139">Dieser Ansatz funktioniert gut, wenn der Host auch einen Pool von wiederverwendbaren arbeitstasks verfügt.</span><span class="sxs-lookup"><span data-stu-id="65cf2-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="65cf2-140">Wenn der Host zerstört eines seiner `IHostTask` Instanzen, zerstört er die entsprechende `ICLRTask` durch Aufrufen von `ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="65cf2-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65cf2-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65cf2-141">Requirements</span></span>  
 <span data-ttu-id="65cf2-142">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65cf2-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65cf2-143">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65cf2-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65cf2-144">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="65cf2-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65cf2-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65cf2-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cf2-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65cf2-146">See Also</span></span>  
 [<span data-ttu-id="65cf2-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65cf2-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="65cf2-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65cf2-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="65cf2-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65cf2-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="65cf2-150">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65cf2-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
