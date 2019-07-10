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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9996b1a84a5f095cf12d74d0c6f594911e7a7788
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770206"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="f0614-102">ICLRTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="f0614-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="f0614-103">Ruft die [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz, die derzeit auf dem Betriebssystem-Thread ausgeführt wird, von dem Aufruf der Methode stammt.</span><span class="sxs-lookup"><span data-stu-id="f0614-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0614-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0614-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0614-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0614-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="f0614-106">[out] Ein Zeiger auf die Adresse einer `ICLRTask` Instanz, die derzeit auf dem Betriebssystem-Thread ausgeführt wird, aus der der Aufruf stammt, oder Null, wenn zurzeit keine Aufgabe in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0614-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0614-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0614-107">Return Value</span></span>  
  
|<span data-ttu-id="f0614-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0614-108">HRESULT</span></span>|<span data-ttu-id="f0614-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0614-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0614-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0614-110">S_OK</span></span>|<span data-ttu-id="f0614-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0614-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="f0614-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0614-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0614-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0614-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0614-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0614-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0614-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0614-115">The call timed out.</span></span>|  
|<span data-ttu-id="f0614-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0614-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0614-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f0614-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0614-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0614-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0614-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f0614-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0614-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0614-120">E_FAIL</span></span>|<span data-ttu-id="f0614-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0614-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0614-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0614-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0614-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f0614-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0614-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0614-124">Remarks</span></span>  
 <span data-ttu-id="f0614-125">Die `ICLRTask` Instanz, die `ppTask` -Parameter zeigt, stellt die aktuell ausgeführte Aufgabe für die CLR.</span><span class="sxs-lookup"><span data-stu-id="f0614-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="f0614-126">Die `ICLRTask` Instanz bezieht sich auf ein entsprechendes [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, die die Aufgabe für den Host darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0614-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0614-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0614-127">Requirements</span></span>  
 <span data-ttu-id="f0614-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0614-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0614-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0614-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0614-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0614-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0614-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0614-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0614-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0614-132">See also</span></span>

- [<span data-ttu-id="f0614-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0614-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f0614-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0614-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f0614-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0614-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f0614-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0614-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
