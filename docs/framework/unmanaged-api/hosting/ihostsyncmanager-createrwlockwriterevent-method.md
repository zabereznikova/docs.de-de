---
title: IHostSyncManager::CreateRWLockWriterEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 5b5faf14337f78d9b176787528ae8947f5810ba6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704369"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="365b6-102">IHostSyncManager::CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="365b6-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="365b6-103">Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.</span><span class="sxs-lookup"><span data-stu-id="365b6-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="365b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="365b6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="365b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="365b6-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="365b6-106">in Ein Cookie, das dem Ereignis für die automatische zurück Setzung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="365b6-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="365b6-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostAutoEvent](ihostautoevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="365b6-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="365b6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="365b6-108">Return Value</span></span>  
  
|<span data-ttu-id="365b6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="365b6-109">HRESULT</span></span>|<span data-ttu-id="365b6-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="365b6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="365b6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="365b6-111">S_OK</span></span>|<span data-ttu-id="365b6-112">`CreateRWLockWriterEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="365b6-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="365b6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="365b6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="365b6-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="365b6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="365b6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="365b6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="365b6-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="365b6-116">The call timed out.</span></span>|  
|<span data-ttu-id="365b6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="365b6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="365b6-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="365b6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="365b6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="365b6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="365b6-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="365b6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="365b6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="365b6-121">E_FAIL</span></span>|<span data-ttu-id="365b6-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="365b6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="365b6-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="365b6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="365b6-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="365b6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="365b6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="365b6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="365b6-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="365b6-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="365b6-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="365b6-127">Remarks</span></span>  

 <span data-ttu-id="365b6-128">Die CLR ruft die- `CreateRWLockWriterEvent` Methode auf, um einen Verweis auf eine- `IHostAutoEvent` Instanz zu erhalten, die bei der Implementierung einer Writer-Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="365b6-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="365b6-129">Der Host kann das angegebene Cookie verwenden, um zu bestimmen, welche Tasks auf die Sperre warten, indem die Iterations Methoden der [ICLRSyncManager](iclrsyncmanager-interface.md) -Schnittstelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="365b6-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="365b6-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="365b6-130">Requirements</span></span>  

 <span data-ttu-id="365b6-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="365b6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="365b6-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="365b6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="365b6-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="365b6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="365b6-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="365b6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365b6-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="365b6-135">See also</span></span>

- [<span data-ttu-id="365b6-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365b6-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="365b6-137">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365b6-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="365b6-138">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365b6-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="365b6-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365b6-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
