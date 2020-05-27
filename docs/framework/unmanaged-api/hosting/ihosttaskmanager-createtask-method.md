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
ms.openlocfilehash: 7079a915c0402df62afa5648317619af82c943b0
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841983"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="4f11f-102">IHostTaskManager::CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="4f11f-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="4f11f-103">Fordert an, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="4f11f-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f11f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f11f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f11f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f11f-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="4f11f-106">in Die angeforderte Größe (in Bytes) des angeforderten Stapels oder 0 (null) für die Standardgröße.</span><span class="sxs-lookup"><span data-stu-id="4f11f-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="4f11f-107">in Ein Zeiger auf die Funktion, die vom Task ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f11f-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="4f11f-108">in Ein Zeiger auf die Benutzerdaten, die an die Funktion übermittelt werden sollen, oder NULL, wenn die Funktion keine Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="4f11f-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="4f11f-109">vorgenommen Ein Zeiger auf die Adresse einer vom Host erstellten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz oder NULL, wenn die Aufgabe nicht erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f11f-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="4f11f-110">Der Task bleibt in einem angehaltenen Zustand, bis er durch einen [IHostTask:: Start](ihosttask-start-method.md)-Befehl explizit gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4f11f-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f11f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4f11f-111">Return Value</span></span>  
  
|<span data-ttu-id="4f11f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f11f-112">HRESULT</span></span>|<span data-ttu-id="4f11f-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4f11f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f11f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f11f-114">S_OK</span></span>|<span data-ttu-id="4f11f-115">`CreateTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4f11f-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="4f11f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f11f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f11f-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4f11f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f11f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f11f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f11f-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="4f11f-119">The call timed out.</span></span>|  
|<span data-ttu-id="4f11f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f11f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f11f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4f11f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f11f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f11f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f11f-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="4f11f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f11f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f11f-124">E_FAIL</span></span>|<span data-ttu-id="4f11f-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4f11f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f11f-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="4f11f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f11f-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4f11f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4f11f-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4f11f-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4f11f-129">Zum Erstellen der angeforderten Aufgabe war nicht genügend Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4f11f-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f11f-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f11f-130">Remarks</span></span>  
 <span data-ttu-id="4f11f-131">Die CLR ruft `CreateTask` auf, um anzufordern, dass der Host eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="4f11f-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="4f11f-132">Der Host gibt einen Schnittstellen Zeiger auf eine- `IHostTask` Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="4f11f-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="4f11f-133">Die zurückgegebene Aufgabe muss angehalten bleiben, bis Sie explizit durch einen-Aufrufvorgang gestartet wird `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="4f11f-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f11f-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f11f-134">Requirements</span></span>  
 <span data-ttu-id="4f11f-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f11f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f11f-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4f11f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f11f-137">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4f11f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f11f-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f11f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f11f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f11f-139">See also</span></span>

- [<span data-ttu-id="4f11f-140">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f11f-140">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4f11f-141">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f11f-141">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4f11f-142">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f11f-142">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4f11f-143">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f11f-143">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
