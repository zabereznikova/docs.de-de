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
ms.openlocfilehash: bf3ddd91a58669540ef310e268162ec78408494f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702028"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="90389-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="90389-102">IHostTaskManager::SwitchToTask Method</span></span>

<span data-ttu-id="90389-103">Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="90389-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90389-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90389-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90389-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90389-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="90389-106">in Einer der [WAIT_OPTION](wait-option-enumeration.md) Enumerationswerte, der die Aktion angibt, die der Host durchführen soll, wenn der angeforderte Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="90389-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90389-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90389-107">Return Value</span></span>  
  
|<span data-ttu-id="90389-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90389-108">HRESULT</span></span>|<span data-ttu-id="90389-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90389-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90389-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="90389-110">S_OK</span></span>|<span data-ttu-id="90389-111">`SwitchToTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90389-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="90389-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90389-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90389-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="90389-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="90389-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="90389-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="90389-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="90389-115">The call timed out.</span></span>|  
|<span data-ttu-id="90389-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="90389-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="90389-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="90389-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="90389-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="90389-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="90389-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="90389-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="90389-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90389-120">E_FAIL</span></span>|<span data-ttu-id="90389-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="90389-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90389-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="90389-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="90389-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="90389-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90389-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90389-124">Remarks</span></span>  

 <span data-ttu-id="90389-125">Der Host kann in einer anderen Aufgabe wie gewünscht oder benötigt wechseln.</span><span class="sxs-lookup"><span data-stu-id="90389-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90389-126">`SwitchToTask` gibt nicht an, zu welcher Aufgabe der Host wechseln soll. Er gibt nur die Aufgabe an, von der er wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="90389-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90389-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90389-127">Requirements</span></span>  

 <span data-ttu-id="90389-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90389-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90389-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="90389-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90389-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="90389-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90389-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90389-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90389-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90389-132">See also</span></span>

- [<span data-ttu-id="90389-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90389-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="90389-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90389-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="90389-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90389-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="90389-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90389-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
