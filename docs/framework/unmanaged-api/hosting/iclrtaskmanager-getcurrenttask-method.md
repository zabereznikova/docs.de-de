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
ms.openlocfilehash: 7db333cd97963ca8ef26673c0ba5cbf352fa331b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165307"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="73e1c-102">ICLRTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="73e1c-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="73e1c-103">Ruft die [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz, die derzeit auf dem Betriebssystem-Thread ausgeführt wird, von dem Aufruf der Methode stammt.</span><span class="sxs-lookup"><span data-stu-id="73e1c-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73e1c-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73e1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="73e1c-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="73e1c-106">[out] Ein Zeiger auf die Adresse einer `ICLRTask` Instanz, die derzeit auf dem Betriebssystem-Thread ausgeführt wird, aus der der Aufruf stammt, oder Null, wenn zurzeit keine Aufgabe in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73e1c-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73e1c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="73e1c-107">Return Value</span></span>  
  
|<span data-ttu-id="73e1c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73e1c-108">HRESULT</span></span>|<span data-ttu-id="73e1c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73e1c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73e1c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="73e1c-110">S_OK</span></span>|<span data-ttu-id="73e1c-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73e1c-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="73e1c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73e1c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73e1c-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="73e1c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73e1c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73e1c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73e1c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="73e1c-115">The call timed out.</span></span>|  
|<span data-ttu-id="73e1c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73e1c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73e1c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="73e1c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73e1c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73e1c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73e1c-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="73e1c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73e1c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73e1c-120">E_FAIL</span></span>|<span data-ttu-id="73e1c-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="73e1c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73e1c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73e1c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73e1c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="73e1c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73e1c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73e1c-124">Remarks</span></span>  
 <span data-ttu-id="73e1c-125">Die `ICLRTask` Instanz, die `ppTask` -Parameter zeigt, stellt die aktuell ausgeführte Aufgabe für die CLR.</span><span class="sxs-lookup"><span data-stu-id="73e1c-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="73e1c-126">Die `ICLRTask` Instanz bezieht sich auf ein entsprechendes [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, die die Aufgabe für den Host darstellt.</span><span class="sxs-lookup"><span data-stu-id="73e1c-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e1c-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73e1c-127">Requirements</span></span>  
 <span data-ttu-id="73e1c-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73e1c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e1c-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73e1c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73e1c-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="73e1c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73e1c-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e1c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e1c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73e1c-132">See also</span></span>

- [<span data-ttu-id="73e1c-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e1c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="73e1c-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e1c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="73e1c-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e1c-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="73e1c-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e1c-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
