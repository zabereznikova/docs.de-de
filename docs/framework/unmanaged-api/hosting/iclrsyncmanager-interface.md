---
title: ICLRSyncManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5406a7a2912554552697c11fd7aa7a2c0e643fa0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="15332-102">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15332-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="15332-103">Definiert Methoden, die Hosts beim Abrufen von Informationen zur angeforderten Aufgaben und zum Erkennen von Deadlocks in seiner Implementierung für die Synchronisierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="15332-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15332-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="15332-104">Methods</span></span>  
  
|<span data-ttu-id="15332-105">Methode</span><span class="sxs-lookup"><span data-stu-id="15332-105">Method</span></span>|<span data-ttu-id="15332-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15332-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15332-107">CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="15332-107">CreateRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="15332-108">Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zum Bestimmen des Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="15332-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="15332-109">DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="15332-109">DeleteRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="15332-110">Fordert an, dass die CLR zerstört einen Iterator, der durch einen Aufruf von erstellten `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="15332-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="15332-111">GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="15332-111">GetMonitorOwner Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="15332-112">Ruft die Aufgabe, die den angegebenen Monitor besitzt.</span><span class="sxs-lookup"><span data-stu-id="15332-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="15332-113">GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="15332-113">GetRWLockOwnerNext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="15332-114">Ruft die nächste Aufgabe, die auf dem aktuellen Lese-/Schreibsperre wartet.</span><span class="sxs-lookup"><span data-stu-id="15332-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15332-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15332-115">Requirements</span></span>  
 <span data-ttu-id="15332-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15332-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15332-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15332-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15332-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15332-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15332-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15332-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15332-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15332-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="15332-121">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15332-121">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="15332-122">Verwaltete und nicht verwaltetes Threading</span><span class="sxs-lookup"><span data-stu-id="15332-122">Managed and Unmanaged Threading</span></span>](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [<span data-ttu-id="15332-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="15332-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
