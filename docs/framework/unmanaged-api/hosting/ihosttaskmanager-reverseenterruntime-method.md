---
title: IHostTaskManager::ReverseEnterRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b30919f6d89f151a93fc46407165279187ef6e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749484"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="0b28a-102">IHostTaskManager::ReverseEnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="0b28a-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="0b28a-103">Benachrichtigt den Host, dass ein Aufruf in der common Language Runtime (CLR) von nicht verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0b28a-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b28a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b28a-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0b28a-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b28a-105">Return Value</span></span>  
  
|<span data-ttu-id="0b28a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b28a-106">HRESULT</span></span>|<span data-ttu-id="0b28a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b28a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b28a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b28a-108">S_OK</span></span>|<span data-ttu-id="0b28a-109">`ReverseEnterRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b28a-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="0b28a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b28a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b28a-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0b28a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b28a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b28a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b28a-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b28a-113">The call timed out.</span></span>|  
|<span data-ttu-id="0b28a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b28a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b28a-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0b28a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b28a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b28a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b28a-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0b28a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b28a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b28a-118">E_FAIL</span></span>|<span data-ttu-id="0b28a-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b28a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b28a-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b28a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b28a-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0b28a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b28a-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0b28a-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0b28a-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Zuordnung der angeforderten Ressource abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0b28a-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b28a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b28a-124">Remarks</span></span>  
 <span data-ttu-id="0b28a-125">Wenn der Aufruf der CLR aus einer Sequenz, die stammen in verwaltetem Code vorgenommen wird, hat jeder Aufruf von `ReverseEnterRuntime` entspricht einem Aufruf von [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="0b28a-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b28a-126">Anrufe können von nicht verwaltetem Code stammen, ohne Verschachtelung.</span><span class="sxs-lookup"><span data-stu-id="0b28a-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="0b28a-127">In diesem Fall besteht kein Aufruf von [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), oder `ReverseLeaveRuntime`, und die Anzahl der Aufrufe von `ReverseEnterRuntime` entspricht nicht der Anzahl der Aufrufe von `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="0b28a-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b28a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b28a-128">Requirements</span></span>  
 <span data-ttu-id="0b28a-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b28a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b28a-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b28a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b28a-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0b28a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b28a-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b28a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b28a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b28a-133">See also</span></span>

- [<span data-ttu-id="0b28a-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b28a-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0b28a-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b28a-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0b28a-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b28a-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0b28a-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b28a-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
