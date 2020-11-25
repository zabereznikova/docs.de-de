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
ms.openlocfilehash: 8a5fc42191634a2e5a441baecc4b78212ffad687
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720491"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="075ef-102">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="075ef-102">IHostSyncManager Interface</span></span>

<span data-ttu-id="075ef-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="075ef-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="075ef-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="075ef-104">Methods</span></span>  
  
|<span data-ttu-id="075ef-105">Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-105">Method</span></span>|<span data-ttu-id="075ef-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="075ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="075ef-107">CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-107">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="075ef-108">Erstellt ein Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="075ef-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="075ef-109">CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-109">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="075ef-110">Erstellt ein kritisches Abschnitts Objekt für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="075ef-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="075ef-111">CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-111">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="075ef-112">Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="075ef-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="075ef-113">CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-113">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="075ef-114">Erstellt ein Ereignis Objekt für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="075ef-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="075ef-115">CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-115">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="075ef-116">Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="075ef-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="075ef-117">CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-117">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="075ef-118">Erstellt ein manuelles Zurücksetzungs Ereignis Objekt für die Implementierung einer Lesesperre.</span><span class="sxs-lookup"><span data-stu-id="075ef-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="075ef-119">CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-119">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="075ef-120">Erstellt ein Ereignis Objekt für die automatische zurück setzung für die Implementierung einer Writer-Sperre.</span><span class="sxs-lookup"><span data-stu-id="075ef-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="075ef-121">CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-121">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="075ef-122">Erstellt ein [IHostSemaphore](ihostsemaphore-interface.md) -Objekt für die CLR, das als Semaphor für warte Ereignisse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="075ef-122">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="075ef-123">SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="075ef-123">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="075ef-124">Legt die [ICLRSyncManager](iclrsyncmanager-interface.md) -Instanz fest, die der aktuellen Instanz zugeordnet werden soll `IHostSyncManager` .</span><span class="sxs-lookup"><span data-stu-id="075ef-124">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="075ef-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="075ef-125">Remarks</span></span>  

 <span data-ttu-id="075ef-126">Die CLR ermittelt die Host Implementierung von, `IHostSyncManager` indem die [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) -Methode mit einem `IID` von IID_IHostSyncManager aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="075ef-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="075ef-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="075ef-127">Requirements</span></span>  

 <span data-ttu-id="075ef-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="075ef-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="075ef-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="075ef-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="075ef-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="075ef-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="075ef-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="075ef-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075ef-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="075ef-132">See also</span></span>

- [<span data-ttu-id="075ef-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="075ef-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="075ef-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="075ef-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
