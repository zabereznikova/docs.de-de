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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913754"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="47f3f-102">IHostTask::SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="47f3f-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="47f3f-103">Fordert an, dass der Host die Thread Prioritätsstufe für den Task anpasst, der durch die aktuelle [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="47f3f-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47f3f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47f3f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47f3f-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="47f3f-106">in Eine ganze Zahl, die den angeforderten Thread Prioritätswert für die Aufgabe darstellt, `IHostTask` die durch die aktuelle Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="47f3f-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47f3f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47f3f-107">Return Value</span></span>  
  
|<span data-ttu-id="47f3f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47f3f-108">HRESULT</span></span>|<span data-ttu-id="47f3f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47f3f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47f3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="47f3f-110">S_OK</span></span>|<span data-ttu-id="47f3f-111">`SetPriority`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47f3f-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="47f3f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47f3f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47f3f-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="47f3f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47f3f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47f3f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47f3f-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="47f3f-115">The call timed out.</span></span>|  
|<span data-ttu-id="47f3f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47f3f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47f3f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="47f3f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47f3f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47f3f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47f3f-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="47f3f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47f3f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47f3f-120">E_FAIL</span></span>|<span data-ttu-id="47f3f-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="47f3f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47f3f-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47f3f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47f3f-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="47f3f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47f3f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47f3f-124">Remarks</span></span>  
 <span data-ttu-id="47f3f-125">Threads erhalten Verarbeitungszeit mithilfe eines Roundrobin-Systems, das teilweise auf der Prioritätsstufe eines Threads basiert.</span><span class="sxs-lookup"><span data-stu-id="47f3f-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="47f3f-126">`SetPriority`ermöglicht der CLR das Festlegen der Thread Prioritätsstufe für die aktuelle Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="47f3f-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="47f3f-127">Die folgenden `newPriority` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="47f3f-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="47f3f-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="47f3f-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="47f3f-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="47f3f-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="47f3f-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="47f3f-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="47f3f-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="47f3f-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="47f3f-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="47f3f-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="47f3f-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="47f3f-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="47f3f-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="47f3f-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="47f3f-135">Die CLR ruft `SetPriority` auf, wenn der Wert <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> von durch Benutzercode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="47f3f-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="47f3f-136">Ein Host kann eigene Algorithmen für die Thread Prioritäts Zuweisung definieren und kann diese Anforderung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="47f3f-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47f3f-137">`SetPriority`meldet nicht, ob die Thread Prioritätsstufe geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="47f3f-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="47f3f-138">Wenden Sie [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) an, um den Wert der Thread Prioritätsstufe der Aufgabe zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="47f3f-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="47f3f-139">Werte der Thread Prioritäts Ebene werden von der `SetThreadPriority` Win32-Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="47f3f-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="47f3f-140">Weitere Informationen zur Thread Priorität finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="47f3f-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f3f-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47f3f-141">Requirements</span></span>  
 <span data-ttu-id="47f3f-142">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47f3f-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f3f-143">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47f3f-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47f3f-144">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47f3f-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47f3f-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47f3f-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f3f-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47f3f-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="47f3f-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47f3f-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="47f3f-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47f3f-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="47f3f-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47f3f-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="47f3f-150">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="47f3f-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="47f3f-151">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47f3f-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
