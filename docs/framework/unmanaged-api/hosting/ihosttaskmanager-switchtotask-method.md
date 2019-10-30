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
ms.openlocfilehash: a55b43f3629cebb0ba1d3a7ac1802126874418d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122117"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="7d871-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="7d871-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="7d871-103">Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d871-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d871-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d871-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d871-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d871-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="7d871-106">in Einer der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Enumerationswerte, der die Aktion angibt, die der Host durchführen soll, wenn der angeforderte Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="7d871-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d871-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d871-107">Return Value</span></span>  
  
|<span data-ttu-id="7d871-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d871-108">HRESULT</span></span>|<span data-ttu-id="7d871-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d871-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d871-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d871-110">S_OK</span></span>|<span data-ttu-id="7d871-111">`SwitchToTask` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7d871-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="7d871-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d871-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d871-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7d871-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d871-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d871-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d871-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7d871-115">The call timed out.</span></span>|  
|<span data-ttu-id="7d871-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d871-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d871-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7d871-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d871-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d871-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d871-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7d871-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d871-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d871-120">E_FAIL</span></span>|<span data-ttu-id="7d871-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7d871-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d871-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d871-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d871-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7d871-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d871-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d871-124">Remarks</span></span>  
 <span data-ttu-id="7d871-125">Der Host kann in einer anderen Aufgabe wie gewünscht oder benötigt wechseln.</span><span class="sxs-lookup"><span data-stu-id="7d871-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d871-126">`SwitchToTask` gibt nicht an, zu welcher Aufgabe der Host wechseln soll. Er gibt nur die Aufgabe an, von der er wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="7d871-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d871-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d871-127">Requirements</span></span>  
 <span data-ttu-id="7d871-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d871-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d871-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7d871-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d871-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7d871-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d871-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d871-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d871-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d871-132">See also</span></span>

- [<span data-ttu-id="7d871-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d871-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7d871-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d871-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d871-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d871-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7d871-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d871-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
