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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200da8b87b52a29c2b075d1e06929031d3f588b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769628"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="29bbc-102">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29bbc-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="29bbc-103">Bietet Methoden, mit die die common Language Runtime (CLR) Synchronisierungsprimitive, die durch Aufrufen des Hosts anstelle der Win32-Synchronisierung-Funktionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="29bbc-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29bbc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="29bbc-104">Methods</span></span>  
  
|<span data-ttu-id="29bbc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-105">Method</span></span>|<span data-ttu-id="29bbc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29bbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29bbc-107">CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="29bbc-108">Erstellt ein automatisches Zurücksetzungsereignis-Objekt.</span><span class="sxs-lookup"><span data-stu-id="29bbc-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="29bbc-109">CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="29bbc-110">Erstellt ein Kritischer Abschnitt-Objekt, für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="29bbc-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="29bbc-111">CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="29bbc-112">Erstellt ein kritisches Abschnittsobjekt mit Spin-Anzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="29bbc-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="29bbc-113">CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="29bbc-114">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="29bbc-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="29bbc-115">CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="29bbc-116">Erstellt ein überwachtes automatisches Zurücksetzungsereignis-Objekt.</span><span class="sxs-lookup"><span data-stu-id="29bbc-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="29bbc-117">CreateRWLockReaderEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="29bbc-118">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt, für die Implementierung der eine Sperre des Lesers.</span><span class="sxs-lookup"><span data-stu-id="29bbc-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="29bbc-119">CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="29bbc-120">Erstellt ein automatisches Zurücksetzungsereignis-Objekt, für die Implementierung von einem Writer-Sperre.</span><span class="sxs-lookup"><span data-stu-id="29bbc-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="29bbc-121">CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="29bbc-122">Erstellt eine [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Objekt für die CLR als Semaphor für Wait-Ereignisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="29bbc-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="29bbc-123">SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="29bbc-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="29bbc-124">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Instanz für die die aktuelle Zuweisung `IHostSyncManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="29bbc-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29bbc-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29bbc-125">Remarks</span></span>  
 <span data-ttu-id="29bbc-126">Die CLR ermittelt, die die Implementierung der Hosts `IHostSyncManager` durch Aufrufen der [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) -Methode mit einer `IID` von IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="29bbc-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29bbc-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29bbc-127">Requirements</span></span>  
 <span data-ttu-id="29bbc-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29bbc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29bbc-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29bbc-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29bbc-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="29bbc-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29bbc-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29bbc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bbc-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29bbc-132">See also</span></span>

- [<span data-ttu-id="29bbc-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29bbc-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="29bbc-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="29bbc-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
