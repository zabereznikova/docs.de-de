---
title: IHostTaskManager::ReverseLeaveRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd3012d966c777749eb800b8986974a4e8d401f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796633"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="1a41b-102">IHostTaskManager::ReverseLeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="1a41b-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="1a41b-103">Benachrichtigt den Host, dass das Steuerelement verlässt die common Language Runtime (CLR) und Eingabe eine nicht verwaltete Funktion, die wiederum aus verwaltetem Code aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a41b-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a41b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a41b-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1a41b-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1a41b-105">Return Value</span></span>  
  
|<span data-ttu-id="1a41b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a41b-106">HRESULT</span></span>|<span data-ttu-id="1a41b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a41b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a41b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a41b-108">S_OK</span></span>|<span data-ttu-id="1a41b-109">`ReverseLeaveRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1a41b-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="1a41b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a41b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a41b-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1a41b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1a41b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a41b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1a41b-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1a41b-113">The call timed out.</span></span>|  
|<span data-ttu-id="1a41b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1a41b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1a41b-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1a41b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1a41b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1a41b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1a41b-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1a41b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1a41b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a41b-118">E_FAIL</span></span>|<span data-ttu-id="1a41b-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1a41b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1a41b-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a41b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1a41b-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1a41b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1a41b-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1a41b-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1a41b-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Zuordnung der angeforderten Ressource abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1a41b-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a41b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a41b-124">Remarks</span></span>  
 <span data-ttu-id="1a41b-125">Die CLR ruft `ReverseLeaveRuntime` um den Host darüber zu informieren, die die aktuell ausgeführte Aufgabe zurückgibt Aufrufen Steuerelements an eine nicht verwaltete Funktion, die wiederum aus verwaltetem Code über Plattformaufrufdienste aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a41b-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="1a41b-126">Jeder Aufruf von `ReverseLeaveRuntime` entspricht einen entsprechenden Aufruf von [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="1a41b-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a41b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a41b-127">Requirements</span></span>  
 <span data-ttu-id="1a41b-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a41b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a41b-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a41b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a41b-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1a41b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a41b-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a41b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a41b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a41b-132">See also</span></span>

- [<span data-ttu-id="1a41b-133">CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="1a41b-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="1a41b-134">EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="1a41b-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="1a41b-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a41b-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1a41b-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a41b-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1a41b-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a41b-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1a41b-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a41b-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="1a41b-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="1a41b-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="1a41b-140">[Genauere Betrachtung von Plattformaufrufen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1a41b-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
