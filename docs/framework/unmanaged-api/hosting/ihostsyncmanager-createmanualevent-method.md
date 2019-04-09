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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ada9a3131ea3063239ab7897d0096f0accbd0f94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137734"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="39616-102">IHostSyncManager::CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="39616-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="39616-103">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="39616-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39616-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39616-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39616-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39616-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="39616-106">[in] `true`, wenn das Objekt signalisiert, andernfalls wird `false`.</span><span class="sxs-lookup"><span data-stu-id="39616-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="39616-107">[out] Ein Zeiger auf die Adresse einer [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder null, wenn das Ereignis konnte nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39616-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39616-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39616-108">Return Value</span></span>  
  
|<span data-ttu-id="39616-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39616-109">HRESULT</span></span>|<span data-ttu-id="39616-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39616-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39616-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="39616-111">S_OK</span></span>|`CreateManualEvent` <span data-ttu-id="39616-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39616-112">returned successfully.</span></span>|  
|<span data-ttu-id="39616-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39616-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39616-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="39616-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39616-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39616-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39616-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="39616-116">The call timed out.</span></span>|  
|<span data-ttu-id="39616-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39616-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39616-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="39616-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39616-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39616-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39616-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="39616-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39616-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39616-121">E_FAIL</span></span>|<span data-ttu-id="39616-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="39616-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39616-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39616-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39616-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="39616-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="39616-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="39616-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="39616-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39616-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39616-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39616-127">Remarks</span></span>  
 `CreateManualEvent` <span data-ttu-id="39616-128">erstellt eine `IHostManualEvent`, ein Ereignis für manuelles Zurücksetzen-Objekt, das einen Aufruf erfordert die [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) Methode, um es auf einen nicht signalisierten Zustand festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39616-128">creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> `CreateManualEvent` <span data-ttu-id="39616-129">spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von `true` für die `bManualReset` Parameter.</span><span class="sxs-lookup"><span data-stu-id="39616-129">mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39616-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39616-130">Requirements</span></span>  
 <span data-ttu-id="39616-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39616-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39616-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39616-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39616-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="39616-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="39616-134">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="39616-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39616-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39616-135">See also</span></span>

- [<span data-ttu-id="39616-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39616-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="39616-137">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39616-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="39616-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39616-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
