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
ms.openlocfilehash: 3a3c42e2877957e3bbf5031e6ba650e4c9e0364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195944"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="cabae-102">ICLRTask::LocksHeld-Methode</span><span class="sxs-lookup"><span data-stu-id="cabae-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="cabae-103">Ruft die Anzahl der Sperren ab, die zurzeit für den Task ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cabae-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cabae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cabae-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cabae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cabae-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="cabae-106">vorgenommen Die Anzahl der Sperren für die Aufgabe zum Zeitpunkt des Methoden Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="cabae-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cabae-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cabae-107">Return Value</span></span>  
  
|<span data-ttu-id="cabae-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cabae-108">HRESULT</span></span>|<span data-ttu-id="cabae-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cabae-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cabae-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cabae-110">S_OK</span></span>|<span data-ttu-id="cabae-111">`LocksHeld` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cabae-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="cabae-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cabae-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cabae-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="cabae-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cabae-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cabae-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cabae-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="cabae-115">The call timed out.</span></span>|  
|<span data-ttu-id="cabae-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cabae-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cabae-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cabae-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cabae-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cabae-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cabae-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="cabae-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cabae-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cabae-120">E_FAIL</span></span>|<span data-ttu-id="cabae-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cabae-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cabae-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cabae-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cabae-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cabae-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cabae-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cabae-124">Requirements</span></span>  
 <span data-ttu-id="cabae-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cabae-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cabae-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cabae-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cabae-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cabae-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cabae-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cabae-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabae-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cabae-129">See also</span></span>

- [<span data-ttu-id="cabae-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cabae-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cabae-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cabae-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cabae-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cabae-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cabae-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cabae-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
