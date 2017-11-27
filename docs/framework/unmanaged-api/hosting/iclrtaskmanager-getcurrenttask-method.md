---
title: ICLRTaskManager::GetCurrentTask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1adf2959beb8687dc3d08ceb7a118bb19a5fa68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="68921-102">ICLRTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="68921-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="68921-103">Ruft die [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz, die derzeit in der Betriebssystem-Thread ausgeführt wird, aus dem Aufruf der Methode stammt.</span><span class="sxs-lookup"><span data-stu-id="68921-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68921-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68921-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68921-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68921-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="68921-106">[out] Ein Zeiger auf die Adresse des ein `ICLRTask` Instanz, die auf dem Betriebssystem-Thread gerade ausgeführt wird, von dem der Aufruf stammt, oder Null, wenn zurzeit keine Aufgabe in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68921-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68921-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="68921-107">Return Value</span></span>  
  
|<span data-ttu-id="68921-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68921-108">HRESULT</span></span>|<span data-ttu-id="68921-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68921-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68921-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="68921-110">S_OK</span></span>|<span data-ttu-id="68921-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68921-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="68921-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="68921-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68921-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="68921-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68921-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68921-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68921-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="68921-115">The call timed out.</span></span>|  
|<span data-ttu-id="68921-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68921-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68921-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="68921-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68921-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68921-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68921-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="68921-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68921-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68921-120">E_FAIL</span></span>|<span data-ttu-id="68921-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="68921-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68921-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="68921-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68921-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="68921-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68921-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68921-124">Remarks</span></span>  
 <span data-ttu-id="68921-125">Die `ICLRTask` Instanz, die `ppTask` -Parameter zeigt, stellt die aktuell ausgeführte Aufgabe für die CLR.</span><span class="sxs-lookup"><span data-stu-id="68921-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="68921-126">Die `ICLRTask` Instanz bezieht sich auf ein entsprechendes [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz, die die Aufgabe für den Host darstellt.</span><span class="sxs-lookup"><span data-stu-id="68921-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68921-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68921-127">Requirements</span></span>  
 <span data-ttu-id="68921-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68921-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68921-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68921-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68921-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68921-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68921-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68921-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68921-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68921-132">See Also</span></span>  
 [<span data-ttu-id="68921-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68921-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="68921-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68921-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="68921-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68921-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="68921-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68921-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
