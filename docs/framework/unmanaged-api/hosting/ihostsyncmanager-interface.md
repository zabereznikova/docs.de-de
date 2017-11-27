---
title: IHostSyncManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="0aaed-102">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0aaed-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="0aaed-103">Enthält Methoden, mit die die common Language Runtime (CLR) Synchronisierungsprimitive erstellen, durch den Host anstelle der Win32-Synchronisierungsfunktionen aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="0aaed-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0aaed-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0aaed-104">Methods</span></span>  
  
|<span data-ttu-id="0aaed-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-105">Method</span></span>|<span data-ttu-id="0aaed-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0aaed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0aaed-107">CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="0aaed-108">Erstellt ein Ereignisobjekt AutoReset.</span><span class="sxs-lookup"><span data-stu-id="0aaed-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="0aaed-109">CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="0aaed-110">Erstellt ein kritisches Abschnittsobjekt für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="0aaed-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="0aaed-111">CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="0aaed-112">Erstellt ein kritisches Abschnittsobjekt mit Spin-Anzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="0aaed-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="0aaed-113">CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="0aaed-114">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="0aaed-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="0aaed-115">CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="0aaed-116">Erstellt ein Ereignisobjekt überwachten AutoReset.</span><span class="sxs-lookup"><span data-stu-id="0aaed-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="0aaed-117">CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="0aaed-118">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt für die Implementierung der eine Sperre des Lesers.</span><span class="sxs-lookup"><span data-stu-id="0aaed-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="0aaed-119">CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="0aaed-120">Erstellt ein Ereignisobjekt AutoReset-für die Implementierung der eine Sperre des Schreibers.</span><span class="sxs-lookup"><span data-stu-id="0aaed-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="0aaed-121">CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="0aaed-122">Erstellt ein [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Objekt für die CLR als Semaphor für Wait-Ereignisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="0aaed-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="0aaed-123">SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaed-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="0aaed-124">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Instanz zuordnen zu den aktuellen `IHostSyncManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="0aaed-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aaed-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0aaed-125">Remarks</span></span>  
 <span data-ttu-id="0aaed-126">Die CLR erkennt die hostimplementierung von `IHostSyncManager` durch Aufrufen der [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) Methode mit einer `IID` von IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="0aaed-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aaed-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0aaed-127">Requirements</span></span>  
 <span data-ttu-id="0aaed-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aaed-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aaed-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0aaed-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0aaed-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0aaed-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0aaed-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aaed-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aaed-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aaed-132">See Also</span></span>  
 [<span data-ttu-id="0aaed-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0aaed-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0aaed-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0aaed-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
