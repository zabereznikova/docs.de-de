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
ms.openlocfilehash: f00d166541f7955516e9d5c1dce2a4342c08ad0a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803148"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="3d761-102">IHostSyncManager::CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="3d761-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="3d761-103">Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.</span><span class="sxs-lookup"><span data-stu-id="3d761-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d761-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d761-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d761-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d761-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="3d761-106">in Ein Cookie, das dem Ereignis für die automatische zurück Setzung zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d761-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="3d761-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostAutoEvent](ihostautoevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="3d761-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d761-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d761-108">Return Value</span></span>  
  
|<span data-ttu-id="3d761-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d761-109">HRESULT</span></span>|<span data-ttu-id="3d761-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3d761-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d761-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d761-111">S_OK</span></span>|<span data-ttu-id="3d761-112">`CreateRWLockWriterEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3d761-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3d761-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d761-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d761-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3d761-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d761-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d761-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d761-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="3d761-116">The call timed out.</span></span>|  
|<span data-ttu-id="3d761-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d761-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d761-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3d761-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d761-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d761-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d761-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="3d761-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d761-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d761-121">E_FAIL</span></span>|<span data-ttu-id="3d761-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3d761-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d761-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="3d761-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d761-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3d761-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3d761-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3d761-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3d761-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d761-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d761-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d761-127">Remarks</span></span>  
 <span data-ttu-id="3d761-128">Die CLR ruft die- `CreateRWLockWriterEvent` Methode auf, um einen Verweis auf eine- `IHostAutoEvent` Instanz zu erhalten, die bei der Implementierung einer Writer-Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d761-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="3d761-129">Der Host kann das angegebene Cookie verwenden, um zu bestimmen, welche Tasks auf die Sperre warten, indem die Iterations Methoden der [ICLRSyncManager](iclrsyncmanager-interface.md) -Schnittstelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3d761-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d761-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d761-130">Requirements</span></span>  
 <span data-ttu-id="3d761-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d761-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d761-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3d761-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d761-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d761-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d761-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d761-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d761-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d761-135">See also</span></span>

- [<span data-ttu-id="3d761-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d761-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3d761-137">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d761-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3d761-138">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d761-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="3d761-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d761-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
