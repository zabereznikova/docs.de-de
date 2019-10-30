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
ms.openlocfilehash: 6ef04799c0062c40f1671cbe6d897a148e1b93bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130470"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="639af-102">IHostGCManager::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="639af-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="639af-103">Benachrichtigt den Host, dass der Common Language Runtime (CLR) die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="639af-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="639af-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="639af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="639af-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="639af-106">in Die Garbage Collection Generierung, die gerade abgeschlossen wird, von der der Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="639af-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="639af-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="639af-107">Return Value</span></span>  
  
|<span data-ttu-id="639af-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="639af-108">HRESULT</span></span>|<span data-ttu-id="639af-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="639af-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="639af-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="639af-110">S_OK</span></span>|<span data-ttu-id="639af-111">`SuspensionEnding` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="639af-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="639af-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="639af-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="639af-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="639af-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="639af-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="639af-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="639af-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="639af-115">The call timed out.</span></span>|  
|<span data-ttu-id="639af-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="639af-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="639af-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="639af-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="639af-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="639af-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="639af-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="639af-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="639af-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="639af-120">E_FAIL</span></span>|<span data-ttu-id="639af-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="639af-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="639af-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="639af-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="639af-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="639af-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="639af-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="639af-124">Remarks</span></span>  
 <span data-ttu-id="639af-125">Die CLR ruft nach dem Ausführen einer Garbage Collection `SuspensionEnding` auf, um den Host darüber zu informieren, dass die Ausführung des Threads fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="639af-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="639af-126">Planen Sie nicht den Thread, von dem aus der Methodenaufrufe durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="639af-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639af-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="639af-127">Requirements</span></span>  
 <span data-ttu-id="639af-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639af-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639af-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="639af-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="639af-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="639af-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="639af-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639af-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639af-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="639af-132">See also</span></span>

- [<span data-ttu-id="639af-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639af-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="639af-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639af-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="639af-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639af-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="639af-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639af-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="639af-137">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639af-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
