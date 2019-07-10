---
title: ICLRTaskManager::CreateTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804a295cf74067eb23ed8e8c860252a1f2fcf5d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770189"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="d168f-102">ICLRTaskManager::CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="d168f-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="d168f-103">Fordert explizit an, dass die common Language Runtime (CLR) eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="d168f-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d168f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d168f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d168f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d168f-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="d168f-106">[out] Ein Zeiger auf die Adresse einer neu erstellten [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), oder Null, wenn der Task konnte nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d168f-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d168f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d168f-107">Return Value</span></span>  
  
|<span data-ttu-id="d168f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d168f-108">HRESULT</span></span>|<span data-ttu-id="d168f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d168f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d168f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d168f-110">S_OK</span></span>|<span data-ttu-id="d168f-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d168f-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="d168f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d168f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d168f-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d168f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d168f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d168f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d168f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d168f-115">The call timed out.</span></span>|  
|<span data-ttu-id="d168f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d168f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d168f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d168f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d168f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d168f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d168f-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d168f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d168f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d168f-120">E_FAIL</span></span>|<span data-ttu-id="d168f-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d168f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d168f-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d168f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d168f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d168f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d168f-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d168f-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d168f-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d168f-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d168f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d168f-126">Remarks</span></span>  
 <span data-ttu-id="d168f-127">Die CLR erstellt eine neue Aufgabe bei der Initialisierung, automatisch, wenn Benutzercode einen Thread erstellt, indem Typen in der <xref:System.Threading> -Namespace, oder wenn die Größe des Threadpools erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="d168f-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="d168f-128">Außerdem erstellt Aufgaben, wenn es sich bei nicht verwalteter Code für eine verwaltete Funktion aufruft.</span><span class="sxs-lookup"><span data-stu-id="d168f-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="d168f-129">`CreateTask` ermöglicht dem Host, stellen eine explizite Anforderung, dass die CLR Erstellen eines neuen Tasks.</span><span class="sxs-lookup"><span data-stu-id="d168f-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="d168f-130">Der Host kann beispielsweise diese Methode, um die Datenstrukturen im Voraus zu initialisieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d168f-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d168f-131">Die neue Aufgabe in einem angehaltenen Zustand zurückgegeben wird und bleibt angehalten, bis der Host explizit aufruft [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="d168f-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d168f-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d168f-132">Requirements</span></span>  
 <span data-ttu-id="d168f-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d168f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d168f-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d168f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d168f-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d168f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d168f-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d168f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d168f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d168f-137">See also</span></span>

- [<span data-ttu-id="d168f-138">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d168f-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d168f-139">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d168f-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d168f-140">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d168f-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d168f-141">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d168f-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
