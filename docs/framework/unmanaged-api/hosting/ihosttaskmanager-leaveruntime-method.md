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
ms.openlocfilehash: 81da8052b79047933b4afc6d5686029465d83eba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191496"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="58d3f-102">IHostTaskManager::LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="58d3f-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="58d3f-103">Benachrichtigt den Host aus, die aktuell ausgeführte Aufgabe ist, lassen die common Language Runtime (CLR) und geben nicht verwalteten Code zu.</span><span class="sxs-lookup"><span data-stu-id="58d3f-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58d3f-104">Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host, dass die aktuell ausgeführte Aufgabe wieder in verwaltetem Code eintritt.</span><span class="sxs-lookup"><span data-stu-id="58d3f-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d3f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58d3f-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d3f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="58d3f-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="58d3f-107">[in] Die Adresse innerhalb der zugeordneten portierbaren ausführbaren Datei der nicht verwaltete Funktion aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58d3f-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58d3f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="58d3f-108">Return Value</span></span>  
  
|<span data-ttu-id="58d3f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58d3f-109">HRESULT</span></span>|<span data-ttu-id="58d3f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58d3f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58d3f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="58d3f-111">S_OK</span></span>|<span data-ttu-id="58d3f-112">`LeaveRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58d3f-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="58d3f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58d3f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58d3f-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="58d3f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58d3f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58d3f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58d3f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="58d3f-116">The call timed out.</span></span>|  
|<span data-ttu-id="58d3f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58d3f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58d3f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="58d3f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58d3f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58d3f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58d3f-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="58d3f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58d3f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58d3f-121">E_FAIL</span></span>|<span data-ttu-id="58d3f-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="58d3f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58d3f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58d3f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58d3f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="58d3f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="58d3f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="58d3f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="58d3f-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuweisung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d3f-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58d3f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58d3f-127">Remarks</span></span>  
 <span data-ttu-id="58d3f-128">Von Aufrufsequenzen an und von nicht verwaltetem Code können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="58d3f-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="58d3f-129">Beispielsweise wird die folgenden Liste beschrieben, eine hypothetische Situation, in denen die Reihenfolge der Aufrufe von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), und `IHostTaskManager::EnterRuntime` ermöglicht es dem Host, um die geschachtelten Ebenen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="58d3f-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="58d3f-130">Aktion</span><span class="sxs-lookup"><span data-stu-id="58d3f-130">Action</span></span>|<span data-ttu-id="58d3f-131">Aufruf der entsprechenden Methode</span><span class="sxs-lookup"><span data-stu-id="58d3f-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="58d3f-132">Eine verwaltete ausführbare Visual Basic-Aufrufe über eine nicht verwaltete Funktion, die mit der Plattform in C geschriebene aufrufen.</span><span class="sxs-lookup"><span data-stu-id="58d3f-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="58d3f-133">Die nicht verwaltete C-Funktion ruft eine Methode in eine verwaltete DLL, die in geschriebenen C#.</span><span class="sxs-lookup"><span data-stu-id="58d3f-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="58d3f-134">Die verwaltete C# Funktion aufruft, eine andere nicht verwaltete Funktion, die in C geschrieben wurden, ebenfalls mit einem Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="58d3f-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="58d3f-135">Die zweite nicht verwaltete Funktion zurück, der Ausführung der C# Funktion.</span><span class="sxs-lookup"><span data-stu-id="58d3f-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="58d3f-136">Die C# Funktion gibt die Ausführung an die erste nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="58d3f-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="58d3f-137">Die erste nicht verwaltete Funktion setzt die Ausführung in Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="58d3f-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="58d3f-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58d3f-138">Requirements</span></span>  
 <span data-ttu-id="58d3f-139">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d3f-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d3f-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58d3f-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58d3f-141">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="58d3f-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58d3f-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d3f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d3f-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58d3f-143">See also</span></span>

- [<span data-ttu-id="58d3f-144">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d3f-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="58d3f-145">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d3f-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="58d3f-146">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d3f-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="58d3f-147">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d3f-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
