---
title: ICLRTaskManager::GetCurrentTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195911"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="8a79d-102">ICLRTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="8a79d-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="8a79d-103">Ruft die [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz ab, die zurzeit auf dem Betriebssystem Thread ausgeführt wird, von dem aus der Methodenaufrufe stammt.</span><span class="sxs-lookup"><span data-stu-id="8a79d-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a79d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a79d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a79d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a79d-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="8a79d-106">vorgenommen Ein Zeiger auf die Adresse einer `ICLRTask`-Instanz, die derzeit auf dem Betriebssystem Thread ausgeführt wird, von dem der-Befehl stammt, oder NULL, wenn zurzeit kein Task in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a79d-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a79d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a79d-107">Return Value</span></span>  
  
|<span data-ttu-id="8a79d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a79d-108">HRESULT</span></span>|<span data-ttu-id="8a79d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a79d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a79d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a79d-110">S_OK</span></span>|<span data-ttu-id="8a79d-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a79d-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="8a79d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a79d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a79d-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8a79d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a79d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a79d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a79d-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8a79d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8a79d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a79d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a79d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8a79d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a79d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a79d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a79d-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8a79d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a79d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a79d-120">E_FAIL</span></span>|<span data-ttu-id="8a79d-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8a79d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a79d-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a79d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a79d-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8a79d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a79d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a79d-124">Remarks</span></span>  
 <span data-ttu-id="8a79d-125">Die `ICLRTask`-Instanz, auf die der `ppTask`-Parameter verweist, stellt die aktuell ausgeführte Aufgabe für die CLR dar.</span><span class="sxs-lookup"><span data-stu-id="8a79d-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="8a79d-126">Die `ICLRTask` Instanz ist einer entsprechenden [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz zugeordnet, die die Aufgabe für den Host darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a79d-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a79d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a79d-127">Requirements</span></span>  
 <span data-ttu-id="8a79d-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a79d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a79d-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8a79d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a79d-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8a79d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a79d-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a79d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a79d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a79d-132">See also</span></span>

- [<span data-ttu-id="8a79d-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a79d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8a79d-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a79d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8a79d-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a79d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8a79d-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a79d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
