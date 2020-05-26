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
ms.openlocfilehash: 334520df749ba428e6480188cd0655bb734725a6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803311"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="78a0d-102">IHostSyncManager::CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="78a0d-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="78a0d-103">Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="78a0d-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78a0d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78a0d-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="78a0d-106">[in] `true` , wenn das Objekt signalisiert wird; andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="78a0d-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="78a0d-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostManualEvent](ihostmanualevent-interface.md) -Instanz oder NULL, wenn das Ereignis nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="78a0d-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78a0d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="78a0d-108">Return Value</span></span>  
  
|<span data-ttu-id="78a0d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78a0d-109">HRESULT</span></span>|<span data-ttu-id="78a0d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78a0d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a0d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="78a0d-111">S_OK</span></span>|<span data-ttu-id="78a0d-112">`CreateManualEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="78a0d-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="78a0d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78a0d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78a0d-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="78a0d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78a0d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78a0d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78a0d-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="78a0d-116">The call timed out.</span></span>|  
|<span data-ttu-id="78a0d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78a0d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78a0d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="78a0d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78a0d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78a0d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78a0d-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="78a0d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78a0d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78a0d-121">E_FAIL</span></span>|<span data-ttu-id="78a0d-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="78a0d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78a0d-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="78a0d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78a0d-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="78a0d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="78a0d-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="78a0d-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="78a0d-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78a0d-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a0d-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78a0d-127">Remarks</span></span>  
 <span data-ttu-id="78a0d-128">`CreateManualEvent`erstellt ein `IHostManualEvent` -Objekt, ein manuelles Zurücksetzungs Ereignis, das einen-Rückruf der [IHostManualEvent:: Reset](ihostmanualevent-reset-method.md) -Methode erfordert, damit es auf einen nicht signalisierten Zustand festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="78a0d-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="78a0d-129">`CreateManualEvent`spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von, der `true` für den-Parameter angegeben ist `bManualReset` .</span><span class="sxs-lookup"><span data-stu-id="78a0d-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a0d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78a0d-130">Requirements</span></span>  
 <span data-ttu-id="78a0d-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a0d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a0d-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="78a0d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78a0d-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="78a0d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a0d-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a0d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a0d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78a0d-135">See also</span></span>

- [<span data-ttu-id="78a0d-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a0d-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="78a0d-137">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a0d-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="78a0d-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a0d-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
