---
title: IHostTaskManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9573891a2c27a2a92eccd0522f84175effa8037a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="7eeaa-102">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eeaa-102">IHostTaskManager Interface</span></span>
<span data-ttu-id="7eeaa-103">Enthält Methoden, die die common Language Runtime (CLR) arbeiten mit Aufgaben, die über den Host anstatt das standard-Betriebssystems threading oder Fiber-Funktionen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7eeaa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7eeaa-104">Methods</span></span>  
  
|<span data-ttu-id="7eeaa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-105">Method</span></span>|<span data-ttu-id="7eeaa-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eeaa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7eeaa-107">BeginDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-107">BeginDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="7eeaa-108">Benachrichtigt der Host, die von Code verwaltetem in eine Phase eintritt, in der die aktuelle Aufgabe nicht abgebrochen werden muss.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="7eeaa-109">BeginThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-109">BeginThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="7eeaa-110">Benachrichtigt der Host, die von Code verwaltetem in einen Punkt eingeben, in dem die aktuelle Aufgabe nicht an einen anderen Betriebssystemthread verschoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="7eeaa-111">CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-111">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="7eeaa-112">Ermöglicht es dem Host anzugeben, ob die common Language Runtime kann den angegebenen Aufruf an eine nicht verwaltete Funktion Inline aus.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="7eeaa-113">CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-113">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|<span data-ttu-id="7eeaa-114">Fordert an, dass der Host eine neue Aufgabe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="7eeaa-115">EndDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-115">EndDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="7eeaa-116">Benachrichtigt der Host, die von Code verwaltetem ist den Zeitraum, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, beenden nach einem vorhergegangenen Aufruf von `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="7eeaa-117">EndThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-117">EndThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="7eeaa-118">Benachrichtigt der Host, die von Code verwaltetem wird den Zeitraum, in dem muss die aktuelle Aufgabe nicht in einen anderen Betriebssystemthread verschoben werden, beendet nach einem vorhergegangenen Aufruf von `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="7eeaa-119">EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-119">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="7eeaa-120">Benachrichtigt den Host, dass ein Aufruf einer Methode, die nicht verwaltete, z. B. einer Plattformaufrufmethode, Steuerung der Ausführung an die CLR zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="7eeaa-121">GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-121">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="7eeaa-122">Ruft einen Schnittstellenzeiger auf die Aufgabe, die gerade auf den Betriebssystemthread ausgeführt wird, von dem dieser Aufruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="7eeaa-123">GetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-123">GetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="7eeaa-124">Ruft die Menge der Stapelspeicherplatz zur Verfügung, die mit Sicherheit zur Verfügung, nachdem ein Stapel-Vorgang abgeschlossen ist, aber vor dem schließenden eines Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="7eeaa-125">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-125">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="7eeaa-126">Benachrichtigt der Host, die von Code verwaltetem ist ein Aufruf an eine nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="7eeaa-127">ReverseEnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-127">ReverseEnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="7eeaa-128">Benachrichtigt den Host, dass die common Language Runtime (CLR) aus nicht verwaltetem Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="7eeaa-129">ReverseLeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-129">ReverseLeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="7eeaa-130">Benachrichtigt, dass das Steuerelement verlässt die CLR und Eingabe eine nicht verwaltete Funktion, die wiederum von verwaltetem Code aufgerufen wurde, den Host.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="7eeaa-131">SetCLRTaskManager-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-131">SetCLRTaskManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="7eeaa-132">Ermöglicht den Host einen Schnittstellenzeiger auf eine [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) Instanz, die von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-132">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="7eeaa-133">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-133">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="7eeaa-134">Benachrichtigt den Host, dass die CLR das Gebietsschema für die aktuelle Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="7eeaa-135">SetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-135">SetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="7eeaa-136">Nur für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="7eeaa-137">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-137">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="7eeaa-138">Benachrichtigt den Host an, dass das Gebietsschema der Benutzeroberfläche für den aktuellen Task geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="7eeaa-139">Sleep-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-139">Sleep Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|<span data-ttu-id="7eeaa-140">Benachrichtigt den Host, dass die aktuelle Aufgabe, in den Energiesparmodus abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="7eeaa-141">SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="7eeaa-141">SwitchToTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="7eeaa-142">Benachrichtigt den Host an, dass er die aktuelle Aufgabe wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eeaa-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7eeaa-143">Remarks</span></span>  
 <span data-ttu-id="7eeaa-144">`IHostTaskManager`ermöglicht es der CLR, Aufgaben, erstellen und verwalten, und es können Hooks für den Host Maßnahmen zu ergreifen, wenn die Steuerung von verwaltetem zu nicht verwaltetem Code und umgekehrt sowie bestimmte Aktionen an der Host kann und kann nicht während der Ausführung von Code erhalten.</span><span class="sxs-lookup"><span data-stu-id="7eeaa-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eeaa-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7eeaa-145">Requirements</span></span>  
 <span data-ttu-id="7eeaa-146">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eeaa-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eeaa-147">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7eeaa-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7eeaa-148">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7eeaa-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7eeaa-149">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eeaa-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eeaa-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eeaa-150">See Also</span></span>  
 [<span data-ttu-id="7eeaa-151">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eeaa-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7eeaa-152">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eeaa-152">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7eeaa-153">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eeaa-153">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7eeaa-154">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7eeaa-154">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
