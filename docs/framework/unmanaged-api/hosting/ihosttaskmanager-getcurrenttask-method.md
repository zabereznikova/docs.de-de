---
title: IHostTaskManager::GetCurrentTask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3ba8cbaac28df49a2df70492c1a292ee8cd287e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="60fac-102">IHostTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="60fac-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="60fac-103">Ruft einen Schnittstellenzeiger auf die Aufgabe, die gerade auf den Betriebssystemthread ausgeführt wird, von dem dieser Aufruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="60fac-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60fac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60fac-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60fac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60fac-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="60fac-106">[out] Ein Zeiger auf die Adresse des ein [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, die die derzeit ausgeführte Aufgabe darstellt.</span><span class="sxs-lookup"><span data-stu-id="60fac-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60fac-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60fac-107">Return Value</span></span>  
  
|<span data-ttu-id="60fac-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60fac-108">HRESULT</span></span>|<span data-ttu-id="60fac-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60fac-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60fac-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="60fac-110">S_OK</span></span>|<span data-ttu-id="60fac-111">`GetCurrentTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="60fac-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="60fac-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="60fac-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60fac-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="60fac-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60fac-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60fac-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60fac-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="60fac-115">The call timed out.</span></span>|  
|<span data-ttu-id="60fac-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60fac-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60fac-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="60fac-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60fac-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60fac-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60fac-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="60fac-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60fac-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60fac-120">E_FAIL</span></span>|<span data-ttu-id="60fac-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="60fac-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60fac-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="60fac-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60fac-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="60fac-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="60fac-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="60fac-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="60fac-125">`GetCurrentTask`ein Thread des Betriebssystems außerhalb der Kontrolle des Hosts wurde aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="60fac-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60fac-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60fac-126">Remarks</span></span>  
 <span data-ttu-id="60fac-127">Der Host kann auch festlegen, die `pTask` Parameter auf null, um zu verhindern, dass eine Aufgabe, die es nicht initiiert haben in der CLR.</span><span class="sxs-lookup"><span data-stu-id="60fac-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60fac-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60fac-128">Requirements</span></span>  
 <span data-ttu-id="60fac-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60fac-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60fac-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60fac-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60fac-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="60fac-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60fac-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60fac-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60fac-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60fac-133">See Also</span></span>  
 [<span data-ttu-id="60fac-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60fac-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="60fac-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60fac-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="60fac-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60fac-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="60fac-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60fac-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
