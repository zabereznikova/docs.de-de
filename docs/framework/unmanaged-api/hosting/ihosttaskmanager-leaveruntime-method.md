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
ms.openlocfilehash: 8ac1c18d094deca50d461ef9ff0933a4f87176e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132990"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="453d3-102">IHostTaskManager::LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="453d3-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="453d3-103">Benachrichtigt den Host, dass die derzeit ausgeführte Aufgabe im Begriff ist, die Common Language Runtime (CLR) zu verlassen und nicht verwalteten Code einzugeben.</span><span class="sxs-lookup"><span data-stu-id="453d3-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="453d3-104">Ein entsprechender Aufruf von [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) benachrichtigt den Host darüber, dass die gerade ausgeführte Aufgabe den verwalteten Code erneut in den Status wechselt.</span><span class="sxs-lookup"><span data-stu-id="453d3-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453d3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="453d3-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="453d3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="453d3-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="453d3-107">in Die Adresse in der zugeordneten portablen ausführbaren Datei der nicht verwalteten Funktion, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="453d3-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="453d3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="453d3-108">Return Value</span></span>  
  
|<span data-ttu-id="453d3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="453d3-109">HRESULT</span></span>|<span data-ttu-id="453d3-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="453d3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="453d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="453d3-111">S_OK</span></span>|<span data-ttu-id="453d3-112">`LeaveRuntime` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="453d3-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="453d3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="453d3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="453d3-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="453d3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="453d3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="453d3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="453d3-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="453d3-116">The call timed out.</span></span>|  
|<span data-ttu-id="453d3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="453d3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="453d3-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="453d3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="453d3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="453d3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="453d3-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="453d3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="453d3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="453d3-121">E_FAIL</span></span>|<span data-ttu-id="453d3-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="453d3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="453d3-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="453d3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="453d3-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="453d3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="453d3-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="453d3-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="453d3-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="453d3-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="453d3-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="453d3-127">Remarks</span></span>  
 <span data-ttu-id="453d3-128">Die Aufrufe von Sequenzen in und aus nicht verwaltetem Code können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="453d3-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="453d3-129">In der folgenden Liste wird z. b. eine hypothetische Situation beschrieben, in der die Sequenz von Aufrufen von `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)und `IHostTaskManager::EnterRuntime` das Erkennen des die-Ebenen.</span><span class="sxs-lookup"><span data-stu-id="453d3-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="453d3-130">Aktion</span><span class="sxs-lookup"><span data-stu-id="453d3-130">Action</span></span>|<span data-ttu-id="453d3-131">Entsprechender Methodenaufrufe</span><span class="sxs-lookup"><span data-stu-id="453d3-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="453d3-132">Eine verwaltete Visual Basic ausführbare Datei Ruft eine nicht verwaltete Funktion auf, die mit einem Platt Form Aufruf in C geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="453d3-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="453d3-133">Die nicht verwaltete C-Funktion Ruft eine Methode in einer verwalteten DLL auf C#, die in geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="453d3-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="453d3-134">Die verwaltete C# Funktion Ruft eine andere in C geschriebene, nicht verwaltete Funktion auf, die auch Platt Form Aufrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="453d3-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="453d3-135">Die zweite nicht verwaltete Funktion gibt die Ausführung an C# die Funktion zurück.</span><span class="sxs-lookup"><span data-stu-id="453d3-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="453d3-136">Die C# -Funktion gibt die Ausführung an die erste nicht verwaltete Funktion zurück.</span><span class="sxs-lookup"><span data-stu-id="453d3-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="453d3-137">Die erste nicht verwaltete Funktion gibt die Ausführung an das Visual Basic Programm zurück.</span><span class="sxs-lookup"><span data-stu-id="453d3-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="453d3-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="453d3-138">Requirements</span></span>  
 <span data-ttu-id="453d3-139">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453d3-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453d3-140">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="453d3-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="453d3-141">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="453d3-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="453d3-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453d3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453d3-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="453d3-143">See also</span></span>

- [<span data-ttu-id="453d3-144">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453d3-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="453d3-145">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453d3-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="453d3-146">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453d3-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="453d3-147">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453d3-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
