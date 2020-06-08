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
ms.openlocfilehash: 1981fdf25440a296801bdbd06c41ebcb4b87e870
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501392"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="b80e9-102">IHostTaskManager::ReverseEnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="b80e9-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="b80e9-103">Benachrichtigt den Host, dass ein-Rückruf aus nicht verwaltetem Code in die Common Language Runtime (CLR) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b80e9-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b80e9-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b80e9-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b80e9-105">Return Value</span></span>  
  
|<span data-ttu-id="b80e9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b80e9-106">HRESULT</span></span>|<span data-ttu-id="b80e9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b80e9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b80e9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b80e9-108">S_OK</span></span>|<span data-ttu-id="b80e9-109">`ReverseEnterRuntime`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b80e9-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b80e9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b80e9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b80e9-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b80e9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b80e9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b80e9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b80e9-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b80e9-113">The call timed out.</span></span>|  
|<span data-ttu-id="b80e9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b80e9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b80e9-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b80e9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b80e9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b80e9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b80e9-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b80e9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b80e9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b80e9-118">E_FAIL</span></span>|<span data-ttu-id="b80e9-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b80e9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b80e9-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="b80e9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b80e9-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b80e9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b80e9-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b80e9-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b80e9-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressourcen Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b80e9-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b80e9-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b80e9-124">Remarks</span></span>  
 <span data-ttu-id="b80e9-125">Wenn der Aufruf der CLR aus einer Sequenz erfolgt, die aus verwaltetem Code stammt, entspricht jeder Aufruf von `ReverseEnterRuntime` einem Aufruf von [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="b80e9-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b80e9-126">Aufrufe können aus nicht verwaltetem Code stammen, ohne dass Sie eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b80e9-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="b80e9-127">In diesem Fall gibt es keinen Aufruf von ' [enumkotime](ihosttaskmanager-enterruntime-method.md)', ' [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)' oder ' ' `ReverseLeaveRuntime` , und die Anzahl der Aufrufe von entspricht `ReverseEnterRuntime` nicht der Anzahl von Aufrufen an `ReverseLeaveRuntime` .</span><span class="sxs-lookup"><span data-stu-id="b80e9-127">In this case, there is no call to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b80e9-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b80e9-128">Requirements</span></span>  
 <span data-ttu-id="b80e9-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b80e9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b80e9-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b80e9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b80e9-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b80e9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b80e9-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b80e9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80e9-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b80e9-133">See also</span></span>

- [<span data-ttu-id="b80e9-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b80e9-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b80e9-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b80e9-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b80e9-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b80e9-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b80e9-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b80e9-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
