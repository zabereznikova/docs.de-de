---
title: IHostTaskManager::ReverseEnterRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseEnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c8d84cbd02527a026206d6fa172a9d3f40683fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="43fb5-102">IHostTaskManager::ReverseEnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="43fb5-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="43fb5-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) aus nicht verwaltetem Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="43fb5-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43fb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43fb5-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="43fb5-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="43fb5-105">Return Value</span></span>  
  
|<span data-ttu-id="43fb5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43fb5-106">HRESULT</span></span>|<span data-ttu-id="43fb5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43fb5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43fb5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="43fb5-108">S_OK</span></span>|<span data-ttu-id="43fb5-109">`ReverseEnterRuntime`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43fb5-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="43fb5-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="43fb5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43fb5-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="43fb5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43fb5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43fb5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43fb5-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="43fb5-113">The call timed out.</span></span>|  
|<span data-ttu-id="43fb5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43fb5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43fb5-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="43fb5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43fb5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43fb5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43fb5-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="43fb5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43fb5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43fb5-118">E_FAIL</span></span>|<span data-ttu-id="43fb5-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="43fb5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43fb5-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="43fb5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43fb5-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="43fb5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="43fb5-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="43fb5-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="43fb5-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Zuordnung der angeforderten Ressource abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="43fb5-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43fb5-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43fb5-124">Remarks</span></span>  
 <span data-ttu-id="43fb5-125">Wenn der Aufruf der CLR aus einer Sequenz, die von stammt in verwaltetem Code vorgenommen wird, hat jeder Aufruf von `ReverseEnterRuntime` entspricht zu einem Aufruf von [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="43fb5-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43fb5-126">Aufrufe können von nicht verwaltetem Code stammen, ohne geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="43fb5-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="43fb5-127">In diesem Fall wird nicht aufgerufen, um [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), oder `ReverseLeaveRuntime`, und die Anzahl der Aufrufe an `ReverseEnterRuntime` entspricht nicht der Anzahl der Aufrufe an `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="43fb5-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43fb5-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43fb5-128">Requirements</span></span>  
 <span data-ttu-id="43fb5-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43fb5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43fb5-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43fb5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43fb5-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43fb5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43fb5-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43fb5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fb5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43fb5-133">See Also</span></span>  
 [<span data-ttu-id="43fb5-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43fb5-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="43fb5-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43fb5-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="43fb5-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43fb5-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="43fb5-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43fb5-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
