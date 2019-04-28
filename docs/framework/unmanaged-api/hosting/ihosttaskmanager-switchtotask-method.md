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
ms.openlocfilehash: a50c9f7fc5921d3e5c21dd3566de81ac2249f3dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796603"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="fa228-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="fa228-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="fa228-103">Benachrichtigt den Host, dass sie die aktuelle Aufgabe wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="fa228-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa228-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa228-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa228-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa228-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="fa228-106">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Enumerationswerte fest, dass die Aktion, die der Host ausführen soll, wenn der angeforderte Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="fa228-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa228-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa228-107">Return Value</span></span>  
  
|<span data-ttu-id="fa228-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa228-108">HRESULT</span></span>|<span data-ttu-id="fa228-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa228-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa228-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa228-110">S_OK</span></span>|<span data-ttu-id="fa228-111">`SwitchToTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa228-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="fa228-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa228-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa228-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa228-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa228-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa228-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa228-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fa228-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa228-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa228-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa228-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fa228-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa228-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa228-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa228-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="fa228-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa228-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa228-120">E_FAIL</span></span>|<span data-ttu-id="fa228-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fa228-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa228-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa228-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa228-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fa228-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa228-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa228-124">Remarks</span></span>  
 <span data-ttu-id="fa228-125">Der Host kann in einer anderen Aufgabe Wunsch oder bei Bedarf wechseln.</span><span class="sxs-lookup"><span data-stu-id="fa228-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa228-126">`SwitchToTask` Welche Aufgabe gibt nicht an der Host wechseln soll; Es gibt nur die Aufgabe, der sie aus wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="fa228-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa228-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa228-127">Requirements</span></span>  
 <span data-ttu-id="fa228-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa228-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa228-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa228-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa228-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fa228-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa228-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa228-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa228-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa228-132">See also</span></span>

- [<span data-ttu-id="fa228-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa228-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fa228-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa228-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fa228-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa228-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fa228-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa228-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
