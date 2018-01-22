---
title: IHostTaskManager::EnterRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70c9e83311fd7427895e1957d3511a45c47434e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="f2456-102">IHostTaskManager::EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="f2456-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="f2456-103">Benachrichtigt den Host an, dass ein Aufruf einer Methode, die nicht verwaltete, z. B. einer Plattformaufrufmethode, Steuerung der Ausführung an die common Language Runtime (CLR) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f2456-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2456-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2456-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f2456-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2456-105">Return Value</span></span>  
  
|<span data-ttu-id="f2456-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2456-106">HRESULT</span></span>|<span data-ttu-id="f2456-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2456-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2456-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2456-108">S_OK</span></span>|<span data-ttu-id="f2456-109">`EnterRuntime`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2456-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="f2456-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2456-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2456-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f2456-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2456-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2456-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2456-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f2456-113">The call timed out.</span></span>|  
|<span data-ttu-id="f2456-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2456-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2456-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f2456-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2456-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2456-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2456-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f2456-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2456-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2456-118">E_FAIL</span></span>|<span data-ttu-id="f2456-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f2456-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2456-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f2456-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2456-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f2456-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f2456-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f2456-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f2456-123">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f2456-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2456-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2456-124">Remarks</span></span>  
 <span data-ttu-id="f2456-125">`EnterRuntime`wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf der [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) -Methode wurde versucht, hat die Ausführung beendet und Steuerung der Ausführung an die Laufzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f2456-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2456-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf `LeaveRuntime` wurde versucht, einen Aufruf in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="f2456-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2456-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2456-127">Requirements</span></span>  
 <span data-ttu-id="f2456-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2456-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2456-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2456-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2456-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2456-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2456-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2456-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2456-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2456-132">See Also</span></span>  
 [<span data-ttu-id="f2456-133">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="f2456-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="f2456-134">Vorgehensweise: Aufrufen von nativen DLLs in verwaltetem Code mithilfe von PInvoke</span><span class="sxs-lookup"><span data-stu-id="f2456-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="f2456-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2456-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f2456-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2456-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f2456-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2456-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f2456-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2456-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="f2456-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="f2456-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
