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
ms.openlocfilehash: 4c05ee766bf40be2e9c39f01c7e1b16cb9fab50d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804839"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="4dfde-102">IHostGCManager::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfde-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="4dfde-103">Benachrichtigt den Host, dass der Common Language Runtime (CLR) die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="4dfde-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dfde-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dfde-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dfde-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4dfde-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="4dfde-106">in Die Garbage Collection Generierung, die gerade abgeschlossen wird, von der der Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="4dfde-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dfde-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4dfde-107">Return Value</span></span>  
  
|<span data-ttu-id="4dfde-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dfde-108">HRESULT</span></span>|<span data-ttu-id="4dfde-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4dfde-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dfde-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dfde-110">S_OK</span></span>|<span data-ttu-id="4dfde-111">`SuspensionEnding`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4dfde-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="4dfde-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4dfde-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4dfde-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4dfde-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4dfde-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4dfde-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4dfde-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="4dfde-115">The call timed out.</span></span>|  
|<span data-ttu-id="4dfde-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4dfde-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4dfde-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4dfde-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4dfde-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4dfde-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4dfde-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="4dfde-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4dfde-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4dfde-120">E_FAIL</span></span>|<span data-ttu-id="4dfde-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4dfde-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4dfde-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="4dfde-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4dfde-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4dfde-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dfde-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4dfde-124">Remarks</span></span>  
 <span data-ttu-id="4dfde-125">Die CLR ruft `SuspensionEnding` auf, nachdem Sie eine Garbage Collection ausgeführt hat, um den Host darüber zu informieren, dass der Thread die Ausführung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="4dfde-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4dfde-126">Planen Sie nicht den Thread, von dem aus der Methodenaufrufe durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="4dfde-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dfde-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dfde-127">Requirements</span></span>  
 <span data-ttu-id="4dfde-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dfde-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dfde-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4dfde-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4dfde-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4dfde-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dfde-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dfde-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfde-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4dfde-132">See also</span></span>

- [<span data-ttu-id="4dfde-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dfde-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4dfde-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dfde-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4dfde-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dfde-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4dfde-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dfde-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="4dfde-137">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dfde-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
