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
ms.openlocfilehash: 7d1511924fc70c42252881a46f8aebb437a3f4f7
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841944"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="98ac3-102">IHostTaskManager::SwitchToTask-Methode</span><span class="sxs-lookup"><span data-stu-id="98ac3-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="98ac3-103">Benachrichtigt den Host, dass der aktuelle Task gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="98ac3-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ac3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98ac3-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98ac3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98ac3-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="98ac3-106">in Einer der [WAIT_OPTION](wait-option-enumeration.md) Enumerationswerte, der die Aktion angibt, die der Host durchführen soll, wenn der angeforderte Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="98ac3-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98ac3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98ac3-107">Return Value</span></span>  
  
|<span data-ttu-id="98ac3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98ac3-108">HRESULT</span></span>|<span data-ttu-id="98ac3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98ac3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98ac3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="98ac3-110">S_OK</span></span>|<span data-ttu-id="98ac3-111">`SwitchToTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98ac3-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="98ac3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98ac3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98ac3-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="98ac3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98ac3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98ac3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98ac3-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="98ac3-115">The call timed out.</span></span>|  
|<span data-ttu-id="98ac3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98ac3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98ac3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="98ac3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98ac3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98ac3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98ac3-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="98ac3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98ac3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98ac3-120">E_FAIL</span></span>|<span data-ttu-id="98ac3-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="98ac3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98ac3-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="98ac3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98ac3-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="98ac3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98ac3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98ac3-124">Remarks</span></span>  
 <span data-ttu-id="98ac3-125">Der Host kann in einer anderen Aufgabe wie gewünscht oder benötigt wechseln.</span><span class="sxs-lookup"><span data-stu-id="98ac3-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98ac3-126">`SwitchToTask`gibt nicht an, zu welcher Aufgabe der Host wechseln soll. Er gibt nur die Aufgabe an, von der er wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="98ac3-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ac3-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98ac3-127">Requirements</span></span>  
 <span data-ttu-id="98ac3-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98ac3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ac3-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="98ac3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98ac3-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="98ac3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98ac3-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98ac3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ac3-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98ac3-132">See also</span></span>

- [<span data-ttu-id="98ac3-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98ac3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="98ac3-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98ac3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="98ac3-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98ac3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="98ac3-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98ac3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
