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
ms.openlocfilehash: 390a29760c0f3680ca082561607ab678e8bd1e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133007"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="7e13e-102">IHostTaskManager::ReverseEnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="7e13e-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="7e13e-103">Benachrichtigt den Host, dass ein-Rückruf aus nicht verwaltetem Code in die Common Language Runtime (CLR) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7e13e-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e13e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e13e-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7e13e-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7e13e-105">Return Value</span></span>  
  
|<span data-ttu-id="7e13e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e13e-106">HRESULT</span></span>|<span data-ttu-id="7e13e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e13e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e13e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e13e-108">S_OK</span></span>|<span data-ttu-id="7e13e-109">`ReverseEnterRuntime` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7e13e-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7e13e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e13e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e13e-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7e13e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e13e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e13e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e13e-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7e13e-113">The call timed out.</span></span>|  
|<span data-ttu-id="7e13e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e13e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e13e-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7e13e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e13e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e13e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e13e-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7e13e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e13e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e13e-118">E_FAIL</span></span>|<span data-ttu-id="7e13e-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7e13e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e13e-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e13e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e13e-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7e13e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7e13e-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7e13e-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7e13e-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressourcen Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7e13e-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e13e-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e13e-124">Remarks</span></span>  
 <span data-ttu-id="7e13e-125">Wenn der Aufruf der CLR aus einer Sequenz erfolgt, die aus verwaltetem Code stammt, entspricht jeder Aufruf von `ReverseEnterRuntime` einem Aufruf von [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="7e13e-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e13e-126">Aufrufe können aus nicht verwaltetem Code stammen, ohne dass Sie eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7e13e-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="7e13e-127">In diesem Fall gibt es keinen Aufruf von " [enumuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)", " [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)" oder "`ReverseLeaveRuntime`", und die Anzahl der Aufrufe an `ReverseEnterRuntime` entspricht nicht der Anzahl von Aufrufen `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="7e13e-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e13e-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e13e-128">Requirements</span></span>  
 <span data-ttu-id="7e13e-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e13e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e13e-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7e13e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e13e-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7e13e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e13e-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e13e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e13e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e13e-133">See also</span></span>

- [<span data-ttu-id="7e13e-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e13e-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7e13e-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e13e-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7e13e-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e13e-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7e13e-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e13e-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
