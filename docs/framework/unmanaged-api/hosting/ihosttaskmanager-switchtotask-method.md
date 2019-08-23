---
title: IHostTaskManager::SwitchToTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4af3d73a4c45654d1d40ef2fbf44a0e2b3e1bf32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913716"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="d78a4-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="d78a4-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="d78a4-103">Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d78a4-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d78a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d78a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d78a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d78a4-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="d78a4-106">in Einer der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Enumerationswerte, der die Aktion angibt, die der Host durchführen soll, wenn der angeforderte Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="d78a4-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d78a4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d78a4-107">Return Value</span></span>  
  
|<span data-ttu-id="d78a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d78a4-108">HRESULT</span></span>|<span data-ttu-id="d78a4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d78a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d78a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d78a4-110">S_OK</span></span>|<span data-ttu-id="d78a4-111">`SwitchToTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d78a4-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="d78a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d78a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d78a4-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d78a4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d78a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d78a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d78a4-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d78a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="d78a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d78a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d78a4-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d78a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d78a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d78a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d78a4-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d78a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d78a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d78a4-120">E_FAIL</span></span>|<span data-ttu-id="d78a4-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d78a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d78a4-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d78a4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d78a4-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d78a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d78a4-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d78a4-124">Remarks</span></span>  
 <span data-ttu-id="d78a4-125">Der Host kann in einer anderen Aufgabe wie gewünscht oder benötigt wechseln.</span><span class="sxs-lookup"><span data-stu-id="d78a4-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d78a4-126">`SwitchToTask`gibt nicht an, zu welcher Aufgabe der Host wechseln soll. Er gibt nur die Aufgabe an, von der er wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="d78a4-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d78a4-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d78a4-127">Requirements</span></span>  
 <span data-ttu-id="d78a4-128">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d78a4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d78a4-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d78a4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d78a4-130">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d78a4-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d78a4-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d78a4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78a4-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d78a4-132">See also</span></span>

- [<span data-ttu-id="d78a4-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d78a4-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d78a4-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d78a4-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d78a4-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d78a4-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d78a4-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d78a4-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
