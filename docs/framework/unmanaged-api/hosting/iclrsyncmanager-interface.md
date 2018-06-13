---
title: ICLRSyncManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436480"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="1e191-102">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e191-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="1e191-103">Definiert Methoden, die Hosts beim Abrufen von Informationen zur angeforderten Aufgaben und zum Erkennen von Deadlocks in seiner Implementierung für die Synchronisierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1e191-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e191-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1e191-104">Methods</span></span>  
  
|<span data-ttu-id="1e191-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1e191-105">Method</span></span>|<span data-ttu-id="1e191-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e191-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e191-107">CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="1e191-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="1e191-108">Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zum Bestimmen des Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="1e191-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="1e191-109">DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="1e191-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="1e191-110">Fordert an, dass die CLR zerstört einen Iterator, der durch einen Aufruf von erstellten `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="1e191-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="1e191-111">GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="1e191-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="1e191-112">Ruft die Aufgabe, die den angegebenen Monitor besitzt.</span><span class="sxs-lookup"><span data-stu-id="1e191-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="1e191-113">GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="1e191-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="1e191-114">Ruft die nächste Aufgabe, die auf dem aktuellen Lese-/Schreibsperre wartet.</span><span class="sxs-lookup"><span data-stu-id="1e191-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e191-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e191-115">Requirements</span></span>  
 <span data-ttu-id="1e191-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e191-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e191-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e191-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e191-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1e191-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e191-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e191-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e191-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e191-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="1e191-121">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e191-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="1e191-122">[Verwaltete und nicht verwaltetes Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e191-122">[Managed and Unmanaged Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span></span>  
 [<span data-ttu-id="1e191-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1e191-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
