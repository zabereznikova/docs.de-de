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
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762967"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="c11a8-102">ICLRTask::Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="c11a8-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="c11a8-103">Informiert den Common Language Runtime (CLR), dass der Host eine Aufgabe abgeschlossen hat, und ermöglicht der CLR die Wiederverwendung der aktuellen [ICLRTask](iclrtask-interface.md) -Instanz, um eine andere Aufgabe darzustellen.</span><span class="sxs-lookup"><span data-stu-id="c11a8-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c11a8-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c11a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c11a8-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="c11a8-106">[in] `true` , wenn die Laufzeit alle Thread bezogenen statischen Werte zurücksetzen soll, zusätzlich zu den Sicherheits-und Gebiets Schema Informationen, die mit der aktuellen `ICLRTask` Instanz verknüpft sind, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="c11a8-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="c11a8-107">Wenn der Wert ist `true` , setzt die Common Language Runtime Daten zurück, die mit oder gespeichert wurden <xref:System.Threading.Thread.AllocateDataSlot%2A> <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="c11a8-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c11a8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c11a8-108">Return Value</span></span>  
  
|<span data-ttu-id="c11a8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c11a8-109">HRESULT</span></span>|<span data-ttu-id="c11a8-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c11a8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c11a8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c11a8-111">S_OK</span></span>|<span data-ttu-id="c11a8-112">`Reset`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c11a8-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="c11a8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c11a8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c11a8-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c11a8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="c11a8-115">erfolgrei</span><span class="sxs-lookup"><span data-stu-id="c11a8-115">successfully</span></span>|  
|<span data-ttu-id="c11a8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c11a8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c11a8-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c11a8-117">The call timed out.</span></span>|  
|<span data-ttu-id="c11a8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c11a8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c11a8-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c11a8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c11a8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c11a8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c11a8-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c11a8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c11a8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c11a8-122">E_FAIL</span></span>|<span data-ttu-id="c11a8-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c11a8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c11a8-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c11a8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c11a8-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c11a8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c11a8-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c11a8-126">Remarks</span></span>  
 <span data-ttu-id="c11a8-127">Die CLR kann zuvor erstellte `ICLRTask` Instanzen wieder verwenden, um den mehr Aufwand zu vermeiden, bei dem jedes Mal, wenn eine neue Aufgabe benötigt wird, neue Instanzen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c11a8-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="c11a8-128">Der Host aktiviert diese Funktion, indem `ICLRTask::Reset` anstelle von [ICLRTask:: ExitTask](iclrtask-exittask-method.md) aufgerufen wird, wenn eine Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c11a8-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="c11a8-129">In der folgenden Liste wird der normale Lebenszyklus einer Instanz von zusammengefasst `ICLRTask` :</span><span class="sxs-lookup"><span data-stu-id="c11a8-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="c11a8-130">Die Laufzeit erstellt eine neue- `ICLRTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="c11a8-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="c11a8-131">Die Laufzeit ruft [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) auf, um einen Verweis auf die aktuelle Host Aufgabe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c11a8-131">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="c11a8-132">Die Laufzeit ruft [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) auf, um die neue Instanz der Host Aufgabe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c11a8-132">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="c11a8-133">Der Task wird ausgeführt und abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c11a8-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="c11a8-134">Der Host zerstört die Aufgabe durch Aufrufen von `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="c11a8-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="c11a8-135">`Reset`ändert dieses Szenario auf zwei Arten.</span><span class="sxs-lookup"><span data-stu-id="c11a8-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="c11a8-136">In Schritt 5 oben wird vom Host aufgerufen, `Reset` um den Task auf einen sauberen Zustand zurückzusetzen, und die Instanz wird dann `ICLRTask` von der zugeordneten [IHostTask](ihosttask-interface.md) -Instanz abgekoppelt.</span><span class="sxs-lookup"><span data-stu-id="c11a8-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="c11a8-137">Falls gewünscht, kann der Host die Instanz auch `IHostTask` zur Wiederverwendung zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="c11a8-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="c11a8-138">In Schritt 1 oben ruft die Laufzeit eine wiederverwendete `ICLRTask` aus dem Cache ab, anstatt eine neue Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c11a8-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="c11a8-139">Diese Vorgehensweise funktioniert gut, wenn der Host auch über einen Pool wiederverwendbarer workertasks verfügt.</span><span class="sxs-lookup"><span data-stu-id="c11a8-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="c11a8-140">Wenn der Host eine seiner Instanzen zerstört `IHostTask` , wird die entsprechende `ICLRTask` durch Aufrufen von zerstört `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="c11a8-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c11a8-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c11a8-141">Requirements</span></span>  
 <span data-ttu-id="c11a8-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c11a8-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c11a8-143">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c11a8-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c11a8-144">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c11a8-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c11a8-145">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c11a8-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11a8-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c11a8-146">See also</span></span>

- [<span data-ttu-id="c11a8-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c11a8-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c11a8-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c11a8-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c11a8-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c11a8-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c11a8-150">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c11a8-150">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
