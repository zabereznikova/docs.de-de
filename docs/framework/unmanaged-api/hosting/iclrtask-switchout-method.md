---
title: ICLRTask::SwitchOut-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: f9c2e77013ff9e31a0a2ef3b4ca511b76ae345e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124599"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="404a6-102">ICLRTask::SwitchOut-Methode</span><span class="sxs-lookup"><span data-stu-id="404a6-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="404a6-103">Benachrichtigt den Common Language Runtime (CLR), dass die durch die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz dargestellte Aufgabe nicht mehr in einem eines ausführbaren-Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="404a6-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="404a6-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="404a6-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="404a6-105">Return Value</span></span>  
  
|<span data-ttu-id="404a6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="404a6-106">HRESULT</span></span>|<span data-ttu-id="404a6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404a6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="404a6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="404a6-108">S_OK</span></span>|<span data-ttu-id="404a6-109">`SwitchOut` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="404a6-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="404a6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="404a6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="404a6-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="404a6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="404a6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="404a6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="404a6-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="404a6-113">The call timed out.</span></span>|  
|<span data-ttu-id="404a6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="404a6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="404a6-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="404a6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="404a6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="404a6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="404a6-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="404a6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="404a6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="404a6-118">E_FAIL</span></span>|<span data-ttu-id="404a6-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="404a6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="404a6-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="404a6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="404a6-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="404a6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="404a6-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="404a6-122">Remarks</span></span>  
 <span data-ttu-id="404a6-123">Ein Host ruft `SwitchOut` auf, um die CLR darüber zu informieren, dass die Ausführung der Aufgabe, die von der aktuellen `ICLRTask` Instanz dargestellt wird, vorübergehend beendet wurde. der Task wird dann neu geplant.</span><span class="sxs-lookup"><span data-stu-id="404a6-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="404a6-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="404a6-124">Requirements</span></span>  
 <span data-ttu-id="404a6-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404a6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404a6-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="404a6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="404a6-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="404a6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="404a6-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404a6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404a6-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="404a6-129">See also</span></span>

- [<span data-ttu-id="404a6-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404a6-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="404a6-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404a6-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="404a6-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404a6-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="404a6-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404a6-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
