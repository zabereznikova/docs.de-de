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
ms.openlocfilehash: 8e0981415c03120cc30e6349daced51e79216938
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669964"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="a3238-102">IHostTaskManager::ReverseLeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="a3238-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>

<span data-ttu-id="a3238-103">Benachrichtigt den Host, dass das Steuerelement die Common Language Runtime (CLR) verlässt und eine nicht verwaltete Funktion eingibt, die wiederum von verwaltetem Code aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a3238-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3238-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3238-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a3238-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3238-105">Return Value</span></span>  
  
|<span data-ttu-id="a3238-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3238-106">HRESULT</span></span>|<span data-ttu-id="a3238-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a3238-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3238-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3238-108">S_OK</span></span>|<span data-ttu-id="a3238-109">`ReverseLeaveRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a3238-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="a3238-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3238-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3238-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a3238-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3238-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3238-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3238-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a3238-113">The call timed out.</span></span>|  
|<span data-ttu-id="a3238-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3238-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3238-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a3238-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3238-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3238-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3238-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a3238-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3238-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3238-118">E_FAIL</span></span>|<span data-ttu-id="a3238-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a3238-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3238-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="a3238-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3238-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a3238-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a3238-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a3238-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a3238-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressourcen Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a3238-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3238-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3238-124">Remarks</span></span>  

 <span data-ttu-id="a3238-125">Die CLR ruft `ReverseLeaveRuntime` auf, um den Host darüber zu informieren, dass die aktuell ausgeführte Aufgabe die Steuerung an eine nicht verwaltete Funktion zurückgibt, die wiederum von verwaltetem Code über Platt Form Aufruf aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a3238-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="a3238-126">Jeder Aufruf von `ReverseLeaveRuntime` entspricht einem entsprechenden Aufruf von [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="a3238-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3238-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a3238-127">Requirements</span></span>  

 <span data-ttu-id="a3238-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3238-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3238-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a3238-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3238-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a3238-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3238-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3238-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3238-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3238-132">See also</span></span>

- [<span data-ttu-id="a3238-133">CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="a3238-133">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="a3238-134">EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="a3238-134">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="a3238-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3238-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a3238-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3238-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a3238-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3238-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a3238-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3238-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="a3238-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="a3238-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="a3238-140">[Genauere Betrachtung von Plattformaufrufen](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a3238-140">[A Closer Look at Platform Invoke](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
