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
ms.openlocfilehash: 67af8f125b2be39138bac5d51148215f3a3acf86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723869"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="c7e86-102">IHostSyncManager::CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="c7e86-102">IHostSyncManager::CreateManualEvent Method</span></span>

<span data-ttu-id="c7e86-103">Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="c7e86-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7e86-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7e86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7e86-105">Parameters</span></span>  

 `bInitialState`  
 <span data-ttu-id="c7e86-106">[in] `true` , wenn das Objekt signalisiert wird; andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="c7e86-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="c7e86-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostManualEvent](ihostmanualevent-interface.md) -Instanz oder NULL, wenn das Ereignis nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c7e86-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7e86-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7e86-108">Return Value</span></span>  
  
|<span data-ttu-id="c7e86-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7e86-109">HRESULT</span></span>|<span data-ttu-id="c7e86-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c7e86-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7e86-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7e86-111">S_OK</span></span>|<span data-ttu-id="c7e86-112">`CreateManualEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7e86-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c7e86-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7e86-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7e86-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c7e86-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7e86-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7e86-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7e86-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c7e86-116">The call timed out.</span></span>|  
|<span data-ttu-id="c7e86-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7e86-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7e86-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c7e86-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7e86-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7e86-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7e86-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c7e86-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7e86-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7e86-121">E_FAIL</span></span>|<span data-ttu-id="c7e86-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c7e86-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7e86-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c7e86-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7e86-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c7e86-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c7e86-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c7e86-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c7e86-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7e86-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e86-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7e86-127">Remarks</span></span>  

 <span data-ttu-id="c7e86-128">`CreateManualEvent` erstellt ein `IHostManualEvent` -Objekt, ein manuelles Zurücksetzungs Ereignis, das einen-Rückruf der [IHostManualEvent:: Reset](ihostmanualevent-reset-method.md) -Methode erfordert, damit es auf einen nicht signalisierten Zustand festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c7e86-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="c7e86-129">`CreateManualEvent` spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von, der `true` für den-Parameter angegeben ist `bManualReset` .</span><span class="sxs-lookup"><span data-stu-id="c7e86-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e86-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7e86-130">Requirements</span></span>  

 <span data-ttu-id="c7e86-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7e86-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7e86-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c7e86-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7e86-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c7e86-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7e86-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e86-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e86-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7e86-135">See also</span></span>

- [<span data-ttu-id="c7e86-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7e86-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c7e86-137">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7e86-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="c7e86-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7e86-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
