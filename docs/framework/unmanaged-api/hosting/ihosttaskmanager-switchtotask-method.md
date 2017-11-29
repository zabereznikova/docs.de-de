---
title: IHostTaskManager::SwitchToTask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SwitchToTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b85c762bd2d10baddfa013a8310e3b542a94af6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="ac132-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="ac132-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="ac132-103">Benachrichtigt den Host an, dass er die aktuelle Aufgabe wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="ac132-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac132-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac132-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac132-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac132-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="ac132-106">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Enumerationswerte, der angibt, der Aktion, die den Host ausführen soll, wenn der angeforderte Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="ac132-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac132-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac132-107">Return Value</span></span>  
  
|<span data-ttu-id="ac132-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac132-108">HRESULT</span></span>|<span data-ttu-id="ac132-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac132-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac132-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac132-110">S_OK</span></span>|<span data-ttu-id="ac132-111">`SwitchToTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ac132-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="ac132-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ac132-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac132-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac132-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac132-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac132-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac132-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ac132-115">The call timed out.</span></span>|  
|<span data-ttu-id="ac132-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac132-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac132-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ac132-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac132-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac132-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac132-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ac132-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac132-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac132-120">E_FAIL</span></span>|<span data-ttu-id="ac132-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ac132-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac132-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ac132-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac132-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ac132-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac132-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac132-124">Remarks</span></span>  
 <span data-ttu-id="ac132-125">Der Host kann in einer anderen Aufgabe Wunsch oder bei Bedarf wechseln.</span><span class="sxs-lookup"><span data-stu-id="ac132-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac132-126">`SwitchToTask`Welche Aufgabe gibt nicht an der Host zu wechseln soll; Es gibt nur die Aufgabe, der sie aus wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="ac132-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac132-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac132-127">Requirements</span></span>  
 <span data-ttu-id="ac132-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac132-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac132-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac132-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac132-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ac132-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac132-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac132-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac132-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac132-132">See Also</span></span>  
 [<span data-ttu-id="ac132-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac132-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ac132-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac132-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ac132-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac132-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ac132-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac132-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
