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
ms.openlocfilehash: 1995321e8598d010188fee2437640b4489eaa294
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472030"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="f5d5a-102">IHostGCManager::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="f5d5a-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="f5d5a-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) die Ausführung von Aufgaben in Threads fortgesetzt wird, die für eine Garbagecollection unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5d5a-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5d5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5d5a-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="f5d5a-106">[in] Die Garbage Collection-Generation, die gerade beendet wird, wird aus dem der Thread wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5d5a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5d5a-107">Return Value</span></span>  
  
|<span data-ttu-id="f5d5a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5d5a-108">HRESULT</span></span>|<span data-ttu-id="f5d5a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5d5a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5d5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5d5a-110">S_OK</span></span>|<span data-ttu-id="f5d5a-111">`SuspensionEnding` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="f5d5a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5d5a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5d5a-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5d5a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5d5a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5d5a-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-115">The call timed out.</span></span>|  
|<span data-ttu-id="f5d5a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5d5a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5d5a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5d5a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5d5a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5d5a-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5d5a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5d5a-120">E_FAIL</span></span>|<span data-ttu-id="f5d5a-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5d5a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5d5a-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5d5a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5d5a-124">Remarks</span></span>  
 <span data-ttu-id="f5d5a-125">Die CLR ruft `SuspensionEnding` nach einer Garbagecollection, um dem Host darüber zu informieren, dass der Thread fortgesetzt wird durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5d5a-126">Ändern Sie nicht den zeitlichen Ablauf des Threads, die, dem von der Methodenaufruf durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f5d5a-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d5a-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5d5a-127">Requirements</span></span>  
 <span data-ttu-id="f5d5a-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5d5a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d5a-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5d5a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5d5a-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5d5a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5d5a-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d5a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d5a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5d5a-132">See also</span></span>
- [<span data-ttu-id="f5d5a-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5d5a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f5d5a-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5d5a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f5d5a-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5d5a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f5d5a-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5d5a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f5d5a-137">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5d5a-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
