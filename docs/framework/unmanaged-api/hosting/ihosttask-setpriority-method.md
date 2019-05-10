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
ms.openlocfilehash: b05960eac85140a1539877eccf2d0ccdf053e76b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64657929"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="51c11-102">IHostTask::SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="51c11-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="51c11-103">Fordert an, dass der Host die Threadpriorität anzupassen, die für die Aufgabe, die vom aktuellen Ebene [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="51c11-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51c11-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51c11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51c11-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="51c11-106">[in] Eine ganze Zahl, die den angeforderten Threadprioritätswert für die Aufgabe, die vom aktuellen darstellt `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="51c11-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51c11-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51c11-107">Return Value</span></span>  
  
|<span data-ttu-id="51c11-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51c11-108">HRESULT</span></span>|<span data-ttu-id="51c11-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51c11-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51c11-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="51c11-110">S_OK</span></span>|<span data-ttu-id="51c11-111">`SetPriority` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51c11-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="51c11-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51c11-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51c11-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51c11-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51c11-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51c11-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51c11-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="51c11-115">The call timed out.</span></span>|  
|<span data-ttu-id="51c11-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51c11-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51c11-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="51c11-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51c11-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51c11-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51c11-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="51c11-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51c11-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51c11-120">E_FAIL</span></span>|<span data-ttu-id="51c11-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="51c11-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51c11-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51c11-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51c11-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="51c11-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51c11-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51c11-124">Remarks</span></span>  
 <span data-ttu-id="51c11-125">Threads Verarbeitungszeit gewährt ein Round-Robin-System, das teilweise auf der Prioritätsstufe eines Threads basierend verwenden.</span><span class="sxs-lookup"><span data-stu-id="51c11-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="51c11-126">`SetPriority` ermöglicht der CLR, Thread-Prioritätsebene für den aktuellen Task festlegen.</span><span class="sxs-lookup"><span data-stu-id="51c11-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="51c11-127">Die folgenden `newPriority` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51c11-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="51c11-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="51c11-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="51c11-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="51c11-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="51c11-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="51c11-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="51c11-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="51c11-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="51c11-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="51c11-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="51c11-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="51c11-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="51c11-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="51c11-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="51c11-135">Die CLR ruft `SetPriority` Wenn der Wert des der <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> durch Benutzercode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="51c11-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="51c11-136">Ein Host kann einen eigenen Algorithmen für die Threadzuweisung-Priorität definieren und ist kostenlos, um diese Anforderung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="51c11-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51c11-137">`SetPriority` gibt keine Auskunft, ob die Prioritätsebene geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="51c11-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="51c11-138">Rufen Sie [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) zum Bestimmen des Werts, der Prioritätsebene der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="51c11-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="51c11-139">Ebene Thread Priority-Werte werden definiert, durch die Win32- `SetThreadPriority` Funktion.</span><span class="sxs-lookup"><span data-stu-id="51c11-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="51c11-140">Weitere Informationen zu Threadpriorität finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="51c11-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c11-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51c11-141">Requirements</span></span>  
 <span data-ttu-id="51c11-142">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c11-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c11-143">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51c11-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51c11-144">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51c11-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51c11-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c11-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c11-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51c11-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="51c11-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51c11-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="51c11-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51c11-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="51c11-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51c11-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="51c11-150">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="51c11-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="51c11-151">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51c11-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
