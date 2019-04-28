---
title: IHostTaskManager::CreateTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eddb11ab56bae5243ea7d00614090bbfe774f71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789445"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="3da30-102">IHostTaskManager::CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="3da30-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="3da30-103">Fordert an, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="3da30-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3da30-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3da30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3da30-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="3da30-106">[in] Die angeforderte Größe der angeforderten Stapel, oder 0 (null) für die standardmäßige Größe in Bytes.</span><span class="sxs-lookup"><span data-stu-id="3da30-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="3da30-107">[in] Ein Zeiger auf die Funktion ist die Aufgabe ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3da30-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="3da30-108">[in] Ein Zeiger auf die Benutzerdaten an die Funktion, oder null, wenn die Funktion übergeben werden, nimmt keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="3da30-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="3da30-109">[out] Ein Zeiger auf die Adresse einer [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz, die vom Host oder Null erstellt werden, wenn der Task kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3da30-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="3da30-110">Die Aufgabe in einem angehaltenen Zustand bleibt, bis sie explizit, durch einen Aufruf von gestartet wird [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="3da30-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da30-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3da30-111">Return Value</span></span>  
  
|<span data-ttu-id="3da30-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3da30-112">HRESULT</span></span>|<span data-ttu-id="3da30-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3da30-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3da30-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3da30-114">S_OK</span></span>|<span data-ttu-id="3da30-115">`CreateTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3da30-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="3da30-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3da30-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3da30-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3da30-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3da30-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3da30-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3da30-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3da30-119">The call timed out.</span></span>|  
|<span data-ttu-id="3da30-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3da30-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3da30-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3da30-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3da30-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3da30-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3da30-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3da30-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3da30-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3da30-124">E_FAIL</span></span>|<span data-ttu-id="3da30-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3da30-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3da30-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3da30-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3da30-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3da30-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3da30-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3da30-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3da30-129">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Aufgabe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3da30-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da30-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3da30-130">Remarks</span></span>  
 <span data-ttu-id="3da30-131">Die CLR ruft `CreateTask` anfordern, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="3da30-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="3da30-132">Der Host gibt einen Schnittstellenzeiger auf ein `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="3da30-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="3da30-133">Die zurückgegebene Aufgabe muss angehalten bleiben, bis sie explizit durch einen Aufruf gestartet wird `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="3da30-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da30-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3da30-134">Requirements</span></span>  
 <span data-ttu-id="3da30-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3da30-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da30-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3da30-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3da30-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3da30-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3da30-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da30-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da30-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da30-139">See also</span></span>

- [<span data-ttu-id="3da30-140">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da30-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3da30-141">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da30-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3da30-142">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da30-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3da30-143">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da30-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
