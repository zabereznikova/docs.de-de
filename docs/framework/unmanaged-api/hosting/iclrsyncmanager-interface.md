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
ms.openlocfilehash: 5bfab21a36becf943b1813f266cf70c4b5e5b1d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690992"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="35093-102">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35093-102">ICLRSyncManager Interface</span></span>

<span data-ttu-id="35093-103">Definiert Methoden, die es dem Host ermöglichen, Informationen zu angeforderten Tasks zu erhalten und Deadlocks in der Synchronisierungs Implementierung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="35093-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35093-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="35093-104">Methods</span></span>  
  
|<span data-ttu-id="35093-105">Methode</span><span class="sxs-lookup"><span data-stu-id="35093-105">Method</span></span>|<span data-ttu-id="35093-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="35093-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35093-107">CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="35093-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="35093-108">Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.</span><span class="sxs-lookup"><span data-stu-id="35093-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="35093-109">DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="35093-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="35093-110">Fordert an, dass die CLR einen Iterator zerstört, der durch einen-Rückruf erstellt wurde `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="35093-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="35093-111">GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="35093-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="35093-112">Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.</span><span class="sxs-lookup"><span data-stu-id="35093-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="35093-113">GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="35093-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="35093-114">Ruft die nächste Aufgabe ab, die auf die aktuelle Lese-/Schreibsperre wartet.</span><span class="sxs-lookup"><span data-stu-id="35093-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35093-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35093-115">Requirements</span></span>  

 <span data-ttu-id="35093-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35093-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35093-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="35093-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35093-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="35093-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35093-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35093-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35093-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35093-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="35093-121">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35093-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="35093-122">[Managed and Unmanaged Threading (Verwaltetes und nicht verwaltetes Threading)](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35093-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="35093-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="35093-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
