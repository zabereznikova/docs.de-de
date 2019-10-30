---
title: IHostSyncManager-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132627"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="d92b1-102">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d92b1-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="d92b1-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d92b1-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d92b1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d92b1-104">Methods</span></span>  
  
|<span data-ttu-id="d92b1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-105">Method</span></span>|<span data-ttu-id="d92b1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d92b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d92b1-107">CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="d92b1-108">Erstellt ein Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d92b1-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="d92b1-109">CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="d92b1-110">Erstellt ein kritisches Abschnitts Objekt für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="d92b1-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="d92b1-111">CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="d92b1-112">Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="d92b1-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="d92b1-113">CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="d92b1-114">Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d92b1-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="d92b1-115">CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="d92b1-116">Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d92b1-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="d92b1-117">CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="d92b1-118">Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.</span><span class="sxs-lookup"><span data-stu-id="d92b1-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="d92b1-119">CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="d92b1-120">Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.</span><span class="sxs-lookup"><span data-stu-id="d92b1-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="d92b1-121">CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="d92b1-122">Erstellt ein [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) -Objekt für die CLR, das als Semaphor für warte Ereignisse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d92b1-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="d92b1-123">SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b1-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="d92b1-124">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) -Instanz fest, die mit der aktuellen `IHostSyncManager` Instanz verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="d92b1-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d92b1-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d92b1-125">Remarks</span></span>  
 <span data-ttu-id="d92b1-126">Die CLR ermittelt die Implementierung des Hosts `IHostSyncManager` durch Aufrufen der [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) -Methode mit einer `IID` von IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="d92b1-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d92b1-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d92b1-127">Requirements</span></span>  
 <span data-ttu-id="d92b1-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d92b1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d92b1-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d92b1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d92b1-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d92b1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d92b1-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d92b1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92b1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d92b1-132">See also</span></span>

- [<span data-ttu-id="d92b1-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d92b1-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d92b1-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d92b1-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
