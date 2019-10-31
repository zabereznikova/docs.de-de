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
ms.openlocfilehash: 64cf6c80ab1cf4b3ca52c60d6e72b54c438f9f4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195836"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="ed27a-102">IHostSyncManager::CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="ed27a-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="ed27a-103">Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.</span><span class="sxs-lookup"><span data-stu-id="ed27a-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed27a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed27a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed27a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed27a-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="ed27a-106">[in] `true`, wenn `ppEvent` signalisiert werden soll. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ed27a-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="ed27a-107">in Ein Cookie, das der Lesesperre zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed27a-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="ed27a-108">vorgenommen Ein Zeiger auf die Adresse einer [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ed27a-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed27a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ed27a-109">Return Value</span></span>  
  
|<span data-ttu-id="ed27a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed27a-110">HRESULT</span></span>|<span data-ttu-id="ed27a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed27a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed27a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed27a-112">S_OK</span></span>|<span data-ttu-id="ed27a-113">`CreateRWLockReaderEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed27a-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ed27a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed27a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed27a-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ed27a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed27a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed27a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed27a-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ed27a-117">The call timed out.</span></span>|  
|<span data-ttu-id="ed27a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed27a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed27a-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ed27a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed27a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed27a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed27a-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ed27a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed27a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed27a-122">E_FAIL</span></span>|<span data-ttu-id="ed27a-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ed27a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed27a-124">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed27a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed27a-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ed27a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed27a-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ed27a-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ed27a-127">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed27a-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed27a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed27a-128">Remarks</span></span>  
 <span data-ttu-id="ed27a-129">Die CLR ruft `CreateRWLockReaderEvent` auf, um einen Verweis auf eine `IHostManualEvent` Instanz zu erhalten, die bei der Implementierung einer Lesesperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed27a-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="ed27a-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Tasks auf die Lesesperre warten, indem die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) -Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="ed27a-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed27a-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed27a-131">Requirements</span></span>  
 <span data-ttu-id="ed27a-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed27a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed27a-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ed27a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed27a-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ed27a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed27a-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed27a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed27a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed27a-136">See also</span></span>

- [<span data-ttu-id="ed27a-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed27a-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ed27a-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed27a-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="ed27a-139">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed27a-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="ed27a-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed27a-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
