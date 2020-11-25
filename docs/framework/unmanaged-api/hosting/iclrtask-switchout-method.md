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
ms.openlocfilehash: 1b27983b3f10eba225442dcd2f5df02062e53ed4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720269"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="c5eaf-102">ICLRTask::SwitchOut-Methode</span><span class="sxs-lookup"><span data-stu-id="c5eaf-102">ICLRTask::SwitchOut Method</span></span>

<span data-ttu-id="c5eaf-103">Benachrichtigt den Common Language Runtime (CLR), dass die durch die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz dargestellte Aufgabe nicht mehr in einem eines ausführbaren-Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5eaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5eaf-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c5eaf-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c5eaf-105">Return Value</span></span>  
  
|<span data-ttu-id="c5eaf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5eaf-106">HRESULT</span></span>|<span data-ttu-id="c5eaf-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c5eaf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5eaf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5eaf-108">S_OK</span></span>|<span data-ttu-id="c5eaf-109">`SwitchOut` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="c5eaf-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5eaf-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5eaf-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5eaf-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5eaf-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5eaf-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-113">The call timed out.</span></span>|  
|<span data-ttu-id="c5eaf-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5eaf-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5eaf-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5eaf-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5eaf-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5eaf-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5eaf-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5eaf-118">E_FAIL</span></span>|<span data-ttu-id="c5eaf-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5eaf-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5eaf-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5eaf-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5eaf-122">Remarks</span></span>  

 <span data-ttu-id="c5eaf-123">Ein Host ruft `SwitchOut` auf, um die CLR darüber zu informieren, dass die Ausführung der Aufgabe, die von der aktuellen `ICLRTask` Instanz dargestellt wird, vorübergehend beendet und der Task neu geplant wird.</span><span class="sxs-lookup"><span data-stu-id="c5eaf-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5eaf-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c5eaf-124">Requirements</span></span>  

 <span data-ttu-id="c5eaf-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5eaf-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5eaf-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c5eaf-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5eaf-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c5eaf-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5eaf-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5eaf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5eaf-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5eaf-129">See also</span></span>

- [<span data-ttu-id="c5eaf-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5eaf-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c5eaf-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5eaf-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c5eaf-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5eaf-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c5eaf-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5eaf-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
