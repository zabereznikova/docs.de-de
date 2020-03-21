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
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177998"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="5b0b9-102">IHostTaskManager::CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="5b0b9-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="5b0b9-103">Fordert an, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b0b9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b0b9-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="5b0b9-106">[in] Die angeforderte Größe (in Bytes) des angeforderten Stapels oder 0 (Null) für die Standardgröße.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="5b0b9-107">[in] Ein Zeiger auf die Funktion, die die Aufgabe ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="5b0b9-108">[in] Ein Zeiger auf die Benutzerdaten, die an die Funktion übergeben werden sollen, oder NULL, wenn die Funktion keine Parameter benötigt.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="5b0b9-109">[out] Ein Zeiger auf die Adresse einer [IHostTask-Instanz,](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) die vom Host erstellt wurde, oder NULL, wenn die Aufgabe nicht erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="5b0b9-110">Die Aufgabe verbleibt in einem angehaltenen Zustand, bis sie explizit durch einen Aufruf von [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b0b9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b0b9-111">Return Value</span></span>  
  
|<span data-ttu-id="5b0b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b0b9-112">HRESULT</span></span>|<span data-ttu-id="5b0b9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b0b9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b0b9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b0b9-114">S_OK</span></span>|<span data-ttu-id="5b0b9-115">`CreateTask`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="5b0b9-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5b0b9-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5b0b9-117">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5b0b9-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5b0b9-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5b0b9-119">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-119">The call timed out.</span></span>|  
|<span data-ttu-id="5b0b9-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5b0b9-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5b0b9-121">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5b0b9-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5b0b9-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5b0b9-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5b0b9-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5b0b9-124">E_FAIL</span></span>|<span data-ttu-id="5b0b9-125">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5b0b9-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5b0b9-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5b0b9-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5b0b9-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5b0b9-129">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Aufgabe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b0b9-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5b0b9-130">Remarks</span></span>  
 <span data-ttu-id="5b0b9-131">Die CLR `CreateTask` ruft auf, um anzufordern, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="5b0b9-132">Der Host gibt einen Schnittstellenzeiger an eine `IHostTask` Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="5b0b9-133">Die zurückgegebene Aufgabe muss angehalten bleiben, bis `IHostTask::Start`sie explizit durch einen Aufruf von gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0b9-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0b9-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5b0b9-134">Requirements</span></span>  
 <span data-ttu-id="5b0b9-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b0b9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0b9-136">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b0b9-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b0b9-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b0b9-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b0b9-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0b9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0b9-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b0b9-139">See also</span></span>

- [<span data-ttu-id="5b0b9-140">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b0b9-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5b0b9-141">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b0b9-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5b0b9-142">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b0b9-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5b0b9-143">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b0b9-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
