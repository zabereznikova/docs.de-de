---
title: IHostSyncManager::CreateAutoEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: 37c306df76a796d6e0a2b7540ebd85c13865dfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682977"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="dbc09-102">IHostSyncManager::CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="dbc09-102">IHostSyncManager::CreateAutoEvent Method</span></span>

<span data-ttu-id="dbc09-103">Erstellt ein Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="dbc09-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbc09-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc09-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbc09-105">Parameters</span></span>  

 `ppEvent`  
 <span data-ttu-id="dbc09-106">vorgenommen Ein Zeiger auf die Adresse einer vom Host implementierten [IHostAutoEvent](ihostautoevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="dbc09-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbc09-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dbc09-107">Return Value</span></span>  
  
|<span data-ttu-id="dbc09-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbc09-108">HRESULT</span></span>|<span data-ttu-id="dbc09-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dbc09-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbc09-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbc09-110">S_OK</span></span>|<span data-ttu-id="dbc09-111">`CreateAutoEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbc09-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="dbc09-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbc09-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbc09-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dbc09-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbc09-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbc09-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbc09-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dbc09-115">The call timed out.</span></span>|  
|<span data-ttu-id="dbc09-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbc09-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbc09-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dbc09-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbc09-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbc09-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbc09-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dbc09-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbc09-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbc09-120">E_FAIL</span></span>|<span data-ttu-id="dbc09-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dbc09-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbc09-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="dbc09-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbc09-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dbc09-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dbc09-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dbc09-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dbc09-125">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbc09-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbc09-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbc09-126">Remarks</span></span>  

 <span data-ttu-id="dbc09-127">`CreateAutoEvent` erstellt ein Auto-Ereignis Objekt, dessen Zustand automatisch in nicht signalisiert geändert wird, nachdem der Warte Thread freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dbc09-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="dbc09-128">Diese Methode spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von, der `false` für den- `bManualReset` Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dbc09-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc09-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dbc09-129">Requirements</span></span>  

 <span data-ttu-id="dbc09-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbc09-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc09-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dbc09-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbc09-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dbc09-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbc09-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc09-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc09-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbc09-134">See also</span></span>

- [<span data-ttu-id="dbc09-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc09-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="dbc09-136">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc09-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="dbc09-137">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc09-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="dbc09-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbc09-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
