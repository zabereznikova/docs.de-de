---
title: IHostSyncManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="18d0e-102">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18d0e-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="18d0e-103">Enthält Methoden, mit die die common Language Runtime (CLR) Synchronisierungsprimitive erstellen, durch den Host anstelle der Win32-Synchronisierungsfunktionen aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="18d0e-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18d0e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="18d0e-104">Methods</span></span>  
  
|<span data-ttu-id="18d0e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-105">Method</span></span>|<span data-ttu-id="18d0e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18d0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18d0e-107">CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="18d0e-108">Erstellt ein Ereignisobjekt AutoReset.</span><span class="sxs-lookup"><span data-stu-id="18d0e-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="18d0e-109">CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="18d0e-110">Erstellt ein kritisches Abschnittsobjekt für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="18d0e-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="18d0e-111">CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="18d0e-112">Erstellt ein kritisches Abschnittsobjekt mit Spin-Anzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="18d0e-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="18d0e-113">CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="18d0e-114">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="18d0e-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="18d0e-115">CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="18d0e-116">Erstellt ein Ereignisobjekt überwachten AutoReset.</span><span class="sxs-lookup"><span data-stu-id="18d0e-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="18d0e-117">CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="18d0e-118">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt für die Implementierung der eine Sperre des Lesers.</span><span class="sxs-lookup"><span data-stu-id="18d0e-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="18d0e-119">CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="18d0e-120">Erstellt ein Ereignisobjekt AutoReset-für die Implementierung der eine Sperre des Schreibers.</span><span class="sxs-lookup"><span data-stu-id="18d0e-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="18d0e-121">CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="18d0e-122">Erstellt ein [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Objekt für die CLR als Semaphor für Wait-Ereignisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="18d0e-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="18d0e-123">SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="18d0e-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="18d0e-124">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Instanz zuordnen zu den aktuellen `IHostSyncManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="18d0e-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18d0e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18d0e-125">Remarks</span></span>  
 <span data-ttu-id="18d0e-126">Die CLR erkennt die hostimplementierung von `IHostSyncManager` durch Aufrufen der [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) Methode mit einer `IID` von IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="18d0e-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18d0e-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18d0e-127">Requirements</span></span>  
 <span data-ttu-id="18d0e-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18d0e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18d0e-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="18d0e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18d0e-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="18d0e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18d0e-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18d0e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d0e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18d0e-132">See Also</span></span>  
 [<span data-ttu-id="18d0e-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18d0e-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="18d0e-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="18d0e-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
