---
title: IHostSyncManager::CreateManualEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195870"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="6e6b5-102">IHostSyncManager::CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="6e6b5-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="6e6b5-103">Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e6b5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e6b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e6b5-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="6e6b5-106">[in] `true`, wenn das Objekt signalisiert wird. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="6e6b5-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder NULL, wenn das Ereignis nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e6b5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e6b5-108">Return Value</span></span>  
  
|<span data-ttu-id="6e6b5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e6b5-109">HRESULT</span></span>|<span data-ttu-id="6e6b5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e6b5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e6b5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e6b5-111">S_OK</span></span>|<span data-ttu-id="6e6b5-112">`CreateManualEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="6e6b5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6e6b5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6e6b5-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6e6b5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6e6b5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6e6b5-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-116">The call timed out.</span></span>|  
|<span data-ttu-id="6e6b5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6e6b5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6e6b5-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6e6b5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6e6b5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6e6b5-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6e6b5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6e6b5-121">E_FAIL</span></span>|<span data-ttu-id="6e6b5-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6e6b5-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6e6b5-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6e6b5-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6e6b5-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6e6b5-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e6b5-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e6b5-127">Remarks</span></span>  
 <span data-ttu-id="6e6b5-128">`CreateManualEvent` erstellt ein `IHostManualEvent`, ein Ereignis Objekt für manuelles Zurücksetzen, das einen-Rückruf der [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) -Methode erfordert, um ihn auf einen nicht signalisierten Zustand festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="6e6b5-129">`CreateManualEvent` spiegelt die Win32-`CreateEvent` Funktion mit dem Wert `true`, der für den `bManualReset`-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e6b5-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6b5-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e6b5-130">Requirements</span></span>  
 <span data-ttu-id="6e6b5-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e6b5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e6b5-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6e6b5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e6b5-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6e6b5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e6b5-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e6b5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6b5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e6b5-135">See also</span></span>

- [<span data-ttu-id="6e6b5-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e6b5-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6e6b5-137">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e6b5-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="6e6b5-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e6b5-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
