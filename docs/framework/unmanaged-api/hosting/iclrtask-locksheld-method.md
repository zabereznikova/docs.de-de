---
title: ICLRTask::LocksHeld-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: 755dfed4107a602390a4402a2dde83e08986b623
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731695"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="16bce-102">ICLRTask::LocksHeld-Methode</span><span class="sxs-lookup"><span data-stu-id="16bce-102">ICLRTask::LocksHeld Method</span></span>

<span data-ttu-id="16bce-103">Ruft die Anzahl der Sperren ab, die zurzeit für den Task ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="16bce-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16bce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16bce-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16bce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="16bce-105">Parameters</span></span>  

 `pLockCount`  
 <span data-ttu-id="16bce-106">vorgenommen Die Anzahl der Sperren für die Aufgabe zum Zeitpunkt des Methoden Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="16bce-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16bce-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16bce-107">Return Value</span></span>  
  
|<span data-ttu-id="16bce-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16bce-108">HRESULT</span></span>|<span data-ttu-id="16bce-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16bce-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16bce-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="16bce-110">S_OK</span></span>|<span data-ttu-id="16bce-111">`LocksHeld` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="16bce-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="16bce-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16bce-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16bce-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="16bce-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16bce-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16bce-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16bce-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="16bce-115">The call timed out.</span></span>|  
|<span data-ttu-id="16bce-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16bce-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16bce-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="16bce-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16bce-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16bce-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16bce-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="16bce-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16bce-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16bce-120">E_FAIL</span></span>|<span data-ttu-id="16bce-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="16bce-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16bce-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="16bce-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16bce-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="16bce-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16bce-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="16bce-124">Requirements</span></span>  

 <span data-ttu-id="16bce-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16bce-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16bce-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="16bce-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16bce-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="16bce-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16bce-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16bce-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16bce-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16bce-129">See also</span></span>

- [<span data-ttu-id="16bce-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16bce-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="16bce-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16bce-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="16bce-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16bce-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="16bce-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16bce-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
