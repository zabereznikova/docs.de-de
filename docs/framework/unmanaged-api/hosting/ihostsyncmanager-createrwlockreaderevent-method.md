---
title: IHostSyncManager::CreateRWLockReaderEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5b640093184e10ef9e3b895ce2328969a45ac9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102569"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="23c9b-102">IHostSyncManager::CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="23c9b-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="23c9b-103">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt, für die Implementierung der eine Sperre des Lesers.</span><span class="sxs-lookup"><span data-stu-id="23c9b-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23c9b-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23c9b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23c9b-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="23c9b-106">[in] `true`, wenn `ppEvent` signalisiert ist, andernfalls sollte `false`.</span><span class="sxs-lookup"><span data-stu-id="23c9b-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="23c9b-107">[in] Ein Cookie, der eine Schreibsperre zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23c9b-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="23c9b-108">[out] Ein Zeiger auf die Adresse einer [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="23c9b-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23c9b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23c9b-109">Return Value</span></span>  
  
|<span data-ttu-id="23c9b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23c9b-110">HRESULT</span></span>|<span data-ttu-id="23c9b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23c9b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23c9b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="23c9b-112">S_OK</span></span>|`CreateRWLockReaderEvent` <span data-ttu-id="23c9b-113">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23c9b-113">returned successfully.</span></span>|  
|<span data-ttu-id="23c9b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23c9b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23c9b-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="23c9b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23c9b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23c9b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23c9b-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23c9b-117">The call timed out.</span></span>|  
|<span data-ttu-id="23c9b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23c9b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23c9b-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="23c9b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23c9b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23c9b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23c9b-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="23c9b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23c9b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23c9b-122">E_FAIL</span></span>|<span data-ttu-id="23c9b-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23c9b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23c9b-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23c9b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23c9b-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="23c9b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23c9b-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="23c9b-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="23c9b-127">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23c9b-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c9b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23c9b-128">Remarks</span></span>  
 <span data-ttu-id="23c9b-129">Die CLR ruft `CreateRWLockReaderEvent` zum Abrufen eines Verweises auf ein `IHostManualEvent` Instanz, die bei der Implementierung der eine Sperre des Lesers.</span><span class="sxs-lookup"><span data-stu-id="23c9b-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="23c9b-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgaben durch Abfragen für die Readersperre warten die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23c9b-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c9b-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23c9b-131">Requirements</span></span>  
 <span data-ttu-id="23c9b-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c9b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c9b-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23c9b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23c9b-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23c9b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="23c9b-135">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="23c9b-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23c9b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23c9b-136">See also</span></span>

- [<span data-ttu-id="23c9b-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c9b-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="23c9b-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c9b-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="23c9b-139">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c9b-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="23c9b-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c9b-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
