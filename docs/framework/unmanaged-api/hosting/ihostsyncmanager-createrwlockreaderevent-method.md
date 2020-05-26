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
ms.openlocfilehash: f3e7456c3f992527981a15b3b1835e1ca72603ad
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803293"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="78a13-102">IHostSyncManager::CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="78a13-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="78a13-103">Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.</span><span class="sxs-lookup"><span data-stu-id="78a13-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78a13-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78a13-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="78a13-106">[in] `true` , wenn `ppEvent` signalisiert werden soll, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="78a13-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="78a13-107">in Ein Cookie, das der Lesesperre zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78a13-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="78a13-108">vorgenommen Ein Zeiger auf die Adresse einer [IHostManualEvent](ihostmanualevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="78a13-108">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78a13-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="78a13-109">Return Value</span></span>  
  
|<span data-ttu-id="78a13-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78a13-110">HRESULT</span></span>|<span data-ttu-id="78a13-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78a13-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a13-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="78a13-112">S_OK</span></span>|<span data-ttu-id="78a13-113">`CreateRWLockReaderEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="78a13-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="78a13-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78a13-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78a13-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="78a13-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78a13-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78a13-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78a13-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="78a13-117">The call timed out.</span></span>|  
|<span data-ttu-id="78a13-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78a13-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78a13-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="78a13-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78a13-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78a13-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78a13-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="78a13-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78a13-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78a13-122">E_FAIL</span></span>|<span data-ttu-id="78a13-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="78a13-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78a13-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="78a13-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78a13-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="78a13-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="78a13-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="78a13-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="78a13-127">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78a13-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a13-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78a13-128">Remarks</span></span>  
 <span data-ttu-id="78a13-129">Die CLR ruft `CreateRWLockReaderEvent` auf, um einen Verweis auf eine- `IHostManualEvent` Instanz zu erhalten, die bei der Implementierung einer Lesesperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78a13-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="78a13-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Tasks auf die Lesesperre warten, indem die [ICLRSyncManager](iclrsyncmanager-interface.md) -Schnittstelle abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="78a13-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a13-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78a13-131">Requirements</span></span>  
 <span data-ttu-id="78a13-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a13-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a13-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="78a13-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78a13-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="78a13-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a13-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a13-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a13-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78a13-136">See also</span></span>

- [<span data-ttu-id="78a13-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a13-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="78a13-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a13-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="78a13-139">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a13-139">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="78a13-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a13-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
