---
title: IHostTaskManager::CallNeedsHostHook-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CallNeedsHostHook
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4774c9f37f73692bf8d9455c51e76aa4c590f925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="87b70-102">IHostTaskManager::CallNeedsHostHook-Methode</span><span class="sxs-lookup"><span data-stu-id="87b70-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="87b70-103">Ermöglicht es dem Host anzugeben, ob die common Language Runtime (CLR) kann den angegebenen Aufruf an eine nicht verwaltete Funktion Inline aus.</span><span class="sxs-lookup"><span data-stu-id="87b70-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87b70-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87b70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87b70-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="87b70-106">[in] Die Adresse innerhalb der zugeordneten PE (portable Executable)-Datei, die nicht verwaltete Funktion, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="87b70-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="87b70-107">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den Aufruf eingebunden werden muss.</span><span class="sxs-lookup"><span data-stu-id="87b70-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87b70-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="87b70-108">Return Value</span></span>  
  
|<span data-ttu-id="87b70-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87b70-109">HRESULT</span></span>|<span data-ttu-id="87b70-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87b70-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87b70-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87b70-111">S_OK</span></span>|<span data-ttu-id="87b70-112">`CallNeedsHostHook`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87b70-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="87b70-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="87b70-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87b70-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="87b70-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87b70-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87b70-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87b70-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="87b70-116">The call timed out.</span></span>|  
|<span data-ttu-id="87b70-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87b70-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87b70-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="87b70-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87b70-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87b70-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87b70-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="87b70-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87b70-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87b70-121">E_FAIL</span></span>|<span data-ttu-id="87b70-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="87b70-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="87b70-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="87b70-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87b70-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="87b70-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87b70-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87b70-125">Remarks</span></span>  
 <span data-ttu-id="87b70-126">Zum Optimieren der Ausführung von Code führt die CLR eine Analyse jeder Plattform Plattformaufrufs während der Kompilierung, um zu bestimmen, ob der Aufruf inline gesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="87b70-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="87b70-127">`CallNeedsHostHook`mit der Host dieser Entscheidung zu überschreiben, indem Sie festlegen, dass ein Aufruf an eine nicht verwaltete Funktion verknüpft werden kann.</span><span class="sxs-lookup"><span data-stu-id="87b70-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="87b70-128">Wenn der Host einen Hook erforderlich ist, kann die Laufzeit den Aufruf nicht Inline.</span><span class="sxs-lookup"><span data-stu-id="87b70-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="87b70-129">Der Host in der Regel einen Hook, müsste ein Gleitkommazustand angepasst werden muss oder nach dem Empfang der Benachrichtigung, dass ein Aufruf einen Zustand eintritt, in dem der Host die Common Language Runtime-Anforderungen für Arbeitsspeicher oder alle Sperren nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="87b70-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="87b70-130">Wenn der Host erfordert, dass der Aufruf verknüpft werden, benachrichtigt die Laufzeit den Host der Übergänge in und aus verwaltetem Code durch Aufrufe [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), und [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="87b70-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b70-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87b70-131">Requirements</span></span>  
 <span data-ttu-id="87b70-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b70-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b70-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87b70-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87b70-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="87b70-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87b70-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b70-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b70-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87b70-136">See Also</span></span>  
 [<span data-ttu-id="87b70-137">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87b70-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="87b70-138">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87b70-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="87b70-139">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87b70-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="87b70-140">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87b70-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
