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
ms.openlocfilehash: 80b4bb2f6a547250acbc16a89e7396c60cc50d87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720450"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="49b79-102">IHostTask::SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="49b79-102">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="49b79-103">Fordert an, dass der Host die Thread Prioritätsstufe für den Task anpasst, der durch die aktuelle [IHostTask](ihosttask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="49b79-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49b79-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b79-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49b79-105">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="49b79-106">in Eine ganze Zahl, die den angeforderten Thread Prioritätswert für die Aufgabe darstellt, die durch die aktuelle Instanz dargestellt wird `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="49b79-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49b79-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="49b79-107">Return Value</span></span>  
  
|<span data-ttu-id="49b79-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49b79-108">HRESULT</span></span>|<span data-ttu-id="49b79-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49b79-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49b79-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="49b79-110">S_OK</span></span>|<span data-ttu-id="49b79-111">`SetPriority` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49b79-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="49b79-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49b79-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49b79-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="49b79-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49b79-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49b79-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49b79-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="49b79-115">The call timed out.</span></span>|  
|<span data-ttu-id="49b79-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49b79-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49b79-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="49b79-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49b79-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49b79-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49b79-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="49b79-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49b79-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49b79-120">E_FAIL</span></span>|<span data-ttu-id="49b79-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="49b79-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49b79-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="49b79-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49b79-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="49b79-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49b79-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49b79-124">Remarks</span></span>  

 <span data-ttu-id="49b79-125">Threads erhalten Verarbeitungszeit mithilfe eines Roundrobin-Systems, das teilweise auf der Prioritätsstufe eines Threads basiert.</span><span class="sxs-lookup"><span data-stu-id="49b79-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="49b79-126">`SetPriority` ermöglicht der CLR das Festlegen der Thread Prioritätsstufe für die aktuelle Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="49b79-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="49b79-127">Die folgenden `newPriority` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49b79-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="49b79-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="49b79-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="49b79-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="49b79-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="49b79-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="49b79-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="49b79-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="49b79-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="49b79-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="49b79-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="49b79-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="49b79-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="49b79-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="49b79-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="49b79-135">Die CLR ruft `SetPriority` auf, wenn der Wert von <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> durch Benutzercode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="49b79-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="49b79-136">Ein Host kann eigene Algorithmen für die Thread Prioritäts Zuweisung definieren und kann diese Anforderung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="49b79-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49b79-137">`SetPriority` meldet nicht, ob die Thread Prioritätsstufe geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="49b79-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="49b79-138">Wenden Sie [IHostTask:: GetPriority](ihosttask-getpriority-method.md) an, um den Wert der Thread Prioritätsstufe der Aufgabe zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="49b79-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="49b79-139">Werte der Thread Prioritäts Ebene werden von der Win32- `SetThreadPriority` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="49b79-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="49b79-140">Weitere Informationen zur Thread Priorität finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="49b79-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b79-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="49b79-141">Requirements</span></span>  

 <span data-ttu-id="49b79-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b79-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b79-143">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="49b79-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49b79-144">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="49b79-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49b79-145">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b79-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b79-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49b79-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="49b79-147">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b79-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="49b79-148">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b79-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="49b79-149">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b79-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="49b79-150">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="49b79-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="49b79-151">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b79-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
