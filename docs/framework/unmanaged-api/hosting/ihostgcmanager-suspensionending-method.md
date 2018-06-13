---
title: IHostGCManager::SuspensionEnding-Methode
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f2835c9846657edffc745c435211f93b20f7173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438833"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="c9f0f-102">IHostGCManager::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="c9f0f-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="c9f0f-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) die Ausführung von Aufgaben in Threads fortgesetzt wird, die für eine Garbagecollection unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9f0f-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9f0f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9f0f-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="c9f0f-106">[in] Die Garbage Collection-Generationen, die gerade beendet wird aus dem der Thread wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9f0f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c9f0f-107">Return Value</span></span>  
  
|<span data-ttu-id="c9f0f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9f0f-108">HRESULT</span></span>|<span data-ttu-id="c9f0f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9f0f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9f0f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9f0f-110">S_OK</span></span>|<span data-ttu-id="c9f0f-111">`SuspensionEnding` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="c9f0f-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c9f0f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9f0f-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9f0f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9f0f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9f0f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9f0f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9f0f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9f0f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9f0f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9f0f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9f0f-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9f0f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9f0f-120">E_FAIL</span></span>|<span data-ttu-id="c9f0f-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9f0f-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9f0f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9f0f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9f0f-124">Remarks</span></span>  
 <span data-ttu-id="c9f0f-125">Die CLR ruft `SuspensionEnding` nachdem es eine Garbagecollection führt, um dem Host darüber zu informieren, dass der Thread die Ausführung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9f0f-126">Planen Sie Threads ein, die vom Aufruf der Methode ausgelöst wurde nicht neu.</span><span class="sxs-lookup"><span data-stu-id="c9f0f-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9f0f-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9f0f-127">Requirements</span></span>  
 <span data-ttu-id="c9f0f-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9f0f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9f0f-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9f0f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9f0f-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c9f0f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9f0f-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9f0f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f0f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9f0f-132">See Also</span></span>  
 [<span data-ttu-id="c9f0f-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f0f-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c9f0f-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f0f-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c9f0f-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f0f-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c9f0f-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f0f-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="c9f0f-137">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f0f-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
