---
title: IHostTaskManager::LeaveRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2059657a6f4543ee29d795ecae7b93b72876fdf4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474630"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="34ed4-102">IHostTaskManager::LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="34ed4-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="34ed4-103">Benachrichtigt den Host aus, die aktuell ausgeführte Aufgabe ist, lassen die common Language Runtime (CLR) und geben nicht verwalteten Code zu.</span><span class="sxs-lookup"><span data-stu-id="34ed4-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34ed4-104">Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host, dass die aktuell ausgeführte Aufgabe wieder in verwaltetem Code eintritt.</span><span class="sxs-lookup"><span data-stu-id="34ed4-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ed4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="34ed4-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34ed4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="34ed4-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="34ed4-107">[in] Die Adresse innerhalb der zugeordneten portierbaren ausführbaren Datei der nicht verwaltete Funktion aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34ed4-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34ed4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34ed4-108">Return Value</span></span>  
  
|<span data-ttu-id="34ed4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34ed4-109">HRESULT</span></span>|<span data-ttu-id="34ed4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34ed4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34ed4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="34ed4-111">S_OK</span></span>|<span data-ttu-id="34ed4-112">`LeaveRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34ed4-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="34ed4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34ed4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34ed4-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34ed4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34ed4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34ed4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34ed4-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34ed4-116">The call timed out.</span></span>|  
|<span data-ttu-id="34ed4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34ed4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34ed4-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="34ed4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34ed4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34ed4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34ed4-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="34ed4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34ed4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34ed4-121">E_FAIL</span></span>|<span data-ttu-id="34ed4-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34ed4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34ed4-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34ed4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34ed4-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="34ed4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="34ed4-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="34ed4-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="34ed4-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuweisung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="34ed4-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34ed4-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34ed4-127">Remarks</span></span>  
 <span data-ttu-id="34ed4-128">Von Aufrufsequenzen an und von nicht verwaltetem Code können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="34ed4-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="34ed4-129">Beispielsweise wird die folgenden Liste beschrieben, eine hypothetische Situation, in denen die Reihenfolge der Aufrufe von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` ermöglicht es dem Host, um die geschachtelten Ebenen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="34ed4-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="34ed4-130">Aktion</span><span class="sxs-lookup"><span data-stu-id="34ed4-130">Action</span></span>|<span data-ttu-id="34ed4-131">Aufruf der entsprechenden Methode</span><span class="sxs-lookup"><span data-stu-id="34ed4-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="34ed4-132">Eine verwaltete ausführbare Visual Basic-Aufrufe über eine nicht verwaltete Funktion, die mit der Plattform in C geschriebene aufrufen.</span><span class="sxs-lookup"><span data-stu-id="34ed4-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="34ed4-133">Die nicht verwaltete C-Funktion ruft eine Methode in eine verwaltete DLL, die in geschriebenen C#.</span><span class="sxs-lookup"><span data-stu-id="34ed4-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="34ed4-134">Die verwaltete C# Funktion aufruft, eine andere nicht verwaltete Funktion, die in C geschrieben wurden, ebenfalls mit einem Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="34ed4-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="34ed4-135">Die zweite nicht verwaltete Funktion zurück, der Ausführung der C# Funktion.</span><span class="sxs-lookup"><span data-stu-id="34ed4-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="34ed4-136">Die C# Funktion gibt die Ausführung an die erste nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="34ed4-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="34ed4-137">Die erste nicht verwaltete Funktion setzt die Ausführung in Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="34ed4-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="34ed4-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34ed4-138">Requirements</span></span>  
 <span data-ttu-id="34ed4-139">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34ed4-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34ed4-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34ed4-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34ed4-141">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="34ed4-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34ed4-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34ed4-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ed4-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34ed4-143">See also</span></span>
- [<span data-ttu-id="34ed4-144">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34ed4-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="34ed4-145">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34ed4-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="34ed4-146">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34ed4-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="34ed4-147">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34ed4-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
