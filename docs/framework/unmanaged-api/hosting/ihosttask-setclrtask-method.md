---
title: IHostTask::SetCLRTask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.SetCLRTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 680ad2c13d8d6fc24134c9399cffb236bd637057
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="b48bf-102">IHostTask::SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="b48bf-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="b48bf-103">Ordnet eine `ICLRTask` Instanz mit dem aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="b48bf-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b48bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b48bf-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b48bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b48bf-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="b48bf-106">[in] Einen Schnittstellenzeiger auf die `ICLRTask` Instanz mit dem aktuellen zugeordnet werden soll `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="b48bf-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b48bf-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b48bf-107">Return Value</span></span>  
  
|<span data-ttu-id="b48bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b48bf-108">HRESULT</span></span>|<span data-ttu-id="b48bf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b48bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b48bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b48bf-110">S_OK</span></span>|<span data-ttu-id="b48bf-111">`SetCLRTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b48bf-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="b48bf-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="b48bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b48bf-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b48bf-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b48bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b48bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b48bf-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b48bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="b48bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b48bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b48bf-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b48bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b48bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b48bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b48bf-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b48bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b48bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b48bf-120">E_FAIL</span></span>|<span data-ttu-id="b48bf-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b48bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b48bf-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b48bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b48bf-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b48bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b48bf-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b48bf-124">Remarks</span></span>  
 <span data-ttu-id="b48bf-125">Die CLR ruft `SetCLRTask` Zuordnen einer `ICLRTask` Instanz mit dem aktuellen `IHostTask` -Instanz, die durch einen Aufruf erstellt wurde [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="b48bf-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b48bf-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b48bf-126">Requirements</span></span>  
 <span data-ttu-id="b48bf-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b48bf-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b48bf-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b48bf-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b48bf-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b48bf-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b48bf-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b48bf-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48bf-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b48bf-131">See Also</span></span>  
 [<span data-ttu-id="b48bf-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b48bf-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b48bf-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b48bf-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b48bf-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b48bf-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b48bf-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b48bf-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
