---
title: IHostTaskManager::EnterRuntime-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a47f51ba32a9dfc16300a8de7c2d4b380a8ba988
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445094"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="9da0c-102">IHostTaskManager::EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="9da0c-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="9da0c-103">Benachrichtigt den Host an, dass ein Aufruf einer Methode, die nicht verwaltete, z. B. einer Plattformaufrufmethode, Steuerung der Ausführung an die common Language Runtime (CLR) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9da0c-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9da0c-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9da0c-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9da0c-105">Return Value</span></span>  
  
|<span data-ttu-id="9da0c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9da0c-106">HRESULT</span></span>|<span data-ttu-id="9da0c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9da0c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9da0c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9da0c-108">S_OK</span></span>|<span data-ttu-id="9da0c-109">`EnterRuntime` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9da0c-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="9da0c-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="9da0c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9da0c-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9da0c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9da0c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9da0c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9da0c-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9da0c-113">The call timed out.</span></span>|  
|<span data-ttu-id="9da0c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9da0c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9da0c-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9da0c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9da0c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9da0c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9da0c-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9da0c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9da0c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9da0c-118">E_FAIL</span></span>|<span data-ttu-id="9da0c-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9da0c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9da0c-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9da0c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9da0c-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9da0c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9da0c-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9da0c-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9da0c-123">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9da0c-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9da0c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9da0c-124">Remarks</span></span>  
 <span data-ttu-id="9da0c-125">`EnterRuntime` wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf der [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) -Methode wurde versucht, hat die Ausführung beendet und Steuerung der Ausführung an die Laufzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9da0c-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9da0c-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf `LeaveRuntime` wurde versucht, einen Aufruf in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="9da0c-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da0c-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9da0c-127">Requirements</span></span>  
 <span data-ttu-id="9da0c-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da0c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da0c-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9da0c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9da0c-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9da0c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9da0c-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da0c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da0c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9da0c-132">See Also</span></span>  
 [<span data-ttu-id="9da0c-133">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9da0c-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="9da0c-134">Vorgehensweise: Aufrufen von nativen DLLs in verwaltetem Code mithilfe von PInvoke</span><span class="sxs-lookup"><span data-stu-id="9da0c-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="9da0c-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9da0c-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9da0c-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9da0c-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9da0c-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9da0c-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9da0c-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9da0c-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="9da0c-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="9da0c-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
