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
ms.openlocfilehash: e4ef2971d9835070e9db72a5e5d370ff35c8edfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106436"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="6ea00-102">IHostTaskManager::EnterRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="6ea00-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="6ea00-103">Benachrichtigt den Host an, dass ein Aufruf an eine nicht verwaltete Methode, wie z. B. eine Plattformaufrufmethode, Steuerung der Ausführung für die common Language Runtime (CLR) beendet wird.</span><span class="sxs-lookup"><span data-stu-id="6ea00-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ea00-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6ea00-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ea00-105">Return Value</span></span>  
  
|<span data-ttu-id="6ea00-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ea00-106">HRESULT</span></span>|<span data-ttu-id="6ea00-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ea00-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ea00-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ea00-108">S_OK</span></span>|`EnterRuntime` <span data-ttu-id="6ea00-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6ea00-109">returned successfully.</span></span>|  
|<span data-ttu-id="6ea00-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ea00-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ea00-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ea00-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ea00-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ea00-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ea00-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6ea00-113">The call timed out.</span></span>|  
|<span data-ttu-id="6ea00-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ea00-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ea00-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6ea00-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ea00-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ea00-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ea00-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="6ea00-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ea00-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ea00-118">E_FAIL</span></span>|<span data-ttu-id="6ea00-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6ea00-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ea00-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ea00-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ea00-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6ea00-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6ea00-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6ea00-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6ea00-123">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Zuweisung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6ea00-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea00-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ea00-124">Remarks</span></span>  
 `EnterRuntime` <span data-ttu-id="6ea00-125">wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf der [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) -Methode wurde versucht, Ausführung abgeschlossen hat und Steuerung der Ausführung an die Laufzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6ea00-125">is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ea00-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) wird aufgerufen, um den Host zu benachrichtigen, die eine nicht verwaltete Funktion, für die einen früheren Aufruf von `LeaveRuntime` wurde versucht, einen Aufruf in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="6ea00-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea00-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ea00-127">Requirements</span></span>  
 <span data-ttu-id="6ea00-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea00-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea00-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ea00-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ea00-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6ea00-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ea00-131">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6ea00-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea00-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ea00-132">See also</span></span>

- [<span data-ttu-id="6ea00-133">Erweiterte COM-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6ea00-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="6ea00-134">Vorgehensweise: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke</span><span class="sxs-lookup"><span data-stu-id="6ea00-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="6ea00-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea00-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6ea00-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea00-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6ea00-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea00-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6ea00-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea00-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="6ea00-139">LeaveRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="6ea00-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
