---
title: IHostTask::SetPriority-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
ms.openlocfilehash: c64cee9ec9b62d87e0c4ae1aafaff59bb985ec95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121353"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="42cf3-102">IHostTask::SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="42cf3-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="42cf3-103">Fordert an, dass der Host die Thread Prioritätsstufe für den Task anpasst, der durch die aktuelle [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="42cf3-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42cf3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42cf3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42cf3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42cf3-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="42cf3-106">in Eine ganze Zahl, die den angeforderten Thread Prioritätswert für die Aufgabe darstellt, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="42cf3-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42cf3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42cf3-107">Return Value</span></span>  
  
|<span data-ttu-id="42cf3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42cf3-108">HRESULT</span></span>|<span data-ttu-id="42cf3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42cf3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42cf3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="42cf3-110">S_OK</span></span>|<span data-ttu-id="42cf3-111">`SetPriority` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42cf3-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="42cf3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42cf3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42cf3-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="42cf3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42cf3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42cf3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42cf3-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="42cf3-115">The call timed out.</span></span>|  
|<span data-ttu-id="42cf3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42cf3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42cf3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="42cf3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42cf3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42cf3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42cf3-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="42cf3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42cf3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42cf3-120">E_FAIL</span></span>|<span data-ttu-id="42cf3-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42cf3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42cf3-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42cf3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42cf3-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="42cf3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42cf3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42cf3-124">Remarks</span></span>  
 <span data-ttu-id="42cf3-125">Threads erhalten Verarbeitungszeit mithilfe eines Roundrobin-Systems, das teilweise auf der Prioritätsstufe eines Threads basiert.</span><span class="sxs-lookup"><span data-stu-id="42cf3-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="42cf3-126">mit `SetPriority` kann die CLR die Thread Prioritätsstufe für die aktuelle Aufgabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="42cf3-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="42cf3-127">Die folgenden `newPriority` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42cf3-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="42cf3-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="42cf3-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="42cf3-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="42cf3-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="42cf3-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="42cf3-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="42cf3-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="42cf3-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="42cf3-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="42cf3-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="42cf3-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="42cf3-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="42cf3-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="42cf3-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="42cf3-135">Die CLR ruft `SetPriority` auf, wenn der Wert des <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> durch Benutzercode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="42cf3-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="42cf3-136">Ein Host kann eigene Algorithmen für die Thread Prioritäts Zuweisung definieren und kann diese Anforderung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="42cf3-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42cf3-137">`SetPriority` meldet nicht, ob die Thread Prioritätsstufe geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="42cf3-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="42cf3-138">Wenden Sie [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) an, um den Wert der Thread Prioritätsstufe der Aufgabe zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="42cf3-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="42cf3-139">Werte der Thread Prioritäts Ebene werden durch die Win32-`SetThreadPriority` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="42cf3-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="42cf3-140">Weitere Informationen zur Thread Priorität finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="42cf3-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42cf3-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42cf3-141">Requirements</span></span>  
 <span data-ttu-id="42cf3-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42cf3-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42cf3-143">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="42cf3-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42cf3-144">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42cf3-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42cf3-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42cf3-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42cf3-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42cf3-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="42cf3-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42cf3-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="42cf3-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42cf3-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="42cf3-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42cf3-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="42cf3-150">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="42cf3-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="42cf3-151">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42cf3-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
