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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118aa3820f422941bea1707dbf7eef2a85027eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439671"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="85031-102">ICLRTask::SwitchOut-Methode</span><span class="sxs-lookup"><span data-stu-id="85031-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="85031-103">Benachrichtigt die common Language Runtime (CLR), die die Aufgabe von der aktuellen dargestellt [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz ist nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="85031-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85031-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85031-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="85031-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85031-105">Return Value</span></span>  
  
|<span data-ttu-id="85031-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85031-106">HRESULT</span></span>|<span data-ttu-id="85031-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85031-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85031-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="85031-108">S_OK</span></span>|<span data-ttu-id="85031-109">`SwitchOut` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85031-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="85031-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="85031-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85031-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="85031-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85031-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85031-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85031-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="85031-113">The call timed out.</span></span>|  
|<span data-ttu-id="85031-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85031-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85031-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="85031-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85031-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85031-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85031-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="85031-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85031-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85031-118">E_FAIL</span></span>|<span data-ttu-id="85031-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="85031-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85031-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="85031-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85031-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="85031-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85031-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85031-122">Remarks</span></span>  
 <span data-ttu-id="85031-123">Ein Host ruft `SwitchOut` , die CLR zu informieren, dass die Ausführung des Tasks vorübergehend unterbrochen wurde, die das aktuelle `ICLRTask` -Instanz darstellt, und Sie den Task neu geplant.</span><span class="sxs-lookup"><span data-stu-id="85031-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85031-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85031-124">Requirements</span></span>  
 <span data-ttu-id="85031-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85031-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85031-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85031-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85031-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85031-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85031-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85031-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85031-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85031-129">See Also</span></span>  
 [<span data-ttu-id="85031-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85031-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="85031-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85031-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="85031-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85031-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="85031-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85031-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
