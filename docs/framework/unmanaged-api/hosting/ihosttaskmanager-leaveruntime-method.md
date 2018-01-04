---
title: IHostTaskManager::LeaveRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4c168cffba44a21d6705e8abd921ecbf8a9da6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="80b6e-102">IHostTaskManager::LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="80b6e-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="80b6e-103">Benachrichtigt den Host, die aktuell ausgeführte Aufgabe ist, lassen Sie die common Language Runtime (CLR), und geben nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="80b6e-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="80b6e-104">Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host, dass die aktuell ausgeführte Aufgabe wieder in verwaltetem Code eintritt.</span><span class="sxs-lookup"><span data-stu-id="80b6e-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b6e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80b6e-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80b6e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="80b6e-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="80b6e-107">[in] Die Adresse innerhalb der zugeordneten übertragbaren ausführbaren Datei der nicht verwalteten Funktion aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="80b6e-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80b6e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80b6e-108">Return Value</span></span>  
  
|<span data-ttu-id="80b6e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80b6e-109">HRESULT</span></span>|<span data-ttu-id="80b6e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80b6e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80b6e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="80b6e-111">S_OK</span></span>|<span data-ttu-id="80b6e-112">`LeaveRuntime`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80b6e-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="80b6e-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="80b6e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80b6e-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="80b6e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80b6e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80b6e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80b6e-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="80b6e-116">The call timed out.</span></span>|  
|<span data-ttu-id="80b6e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80b6e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80b6e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="80b6e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80b6e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80b6e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80b6e-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="80b6e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80b6e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80b6e-121">E_FAIL</span></span>|<span data-ttu-id="80b6e-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="80b6e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80b6e-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="80b6e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80b6e-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="80b6e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="80b6e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="80b6e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="80b6e-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="80b6e-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80b6e-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80b6e-127">Remarks</span></span>  
 <span data-ttu-id="80b6e-128">Von Aufrufsequenzen an und von nicht verwaltetem Code können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="80b6e-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="80b6e-129">Beispielsweise wird die Liste unten beschrieben, eine hypothetische Situation, in der die Reihenfolge der Aufrufe von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` der Host kann geschachtelten Ebenen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="80b6e-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="80b6e-130">Aktion</span><span class="sxs-lookup"><span data-stu-id="80b6e-130">Action</span></span>|<span data-ttu-id="80b6e-131">Entsprechende Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="80b6e-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="80b6e-132">Rufen Sie eine verwaltete ausführbare Visual Basic-ruft eine nicht verwaltete Funktion, die mit der Plattform in C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="80b6e-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="80b6e-133">Die nicht verwaltete C-Funktion ruft eine Methode in eine verwaltete DLL, die in c# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="80b6e-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="80b6e-134">Die verwaltete C#-Funktion aufruft, eine andere nicht verwaltete Funktion, die in C# geschrieben wurde, ebenfalls mit einem Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="80b6e-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="80b6e-135">Die zweite nicht verwaltete Funktion gibt die Ausführung an die C#-Funktion.</span><span class="sxs-lookup"><span data-stu-id="80b6e-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="80b6e-136">Die C#-Funktion gibt die Ausführung an die erste nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="80b6e-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="80b6e-137">Die erste nicht verwaltete Funktion gibt die Ausführung an das Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="80b6e-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="80b6e-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80b6e-138">Requirements</span></span>  
 <span data-ttu-id="80b6e-139">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80b6e-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80b6e-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80b6e-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80b6e-141">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="80b6e-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80b6e-142">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80b6e-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b6e-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80b6e-143">See Also</span></span>  
 [<span data-ttu-id="80b6e-144">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80b6e-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="80b6e-145">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80b6e-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="80b6e-146">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80b6e-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="80b6e-147">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80b6e-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
