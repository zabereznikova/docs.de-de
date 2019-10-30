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
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133935"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="a815f-102">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a815f-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="a815f-103">Definiert Methoden, die es dem Host ermöglichen, Informationen zu angeforderten Tasks zu erhalten und Deadlocks in der Synchronisierungs Implementierung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="a815f-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a815f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a815f-104">Methods</span></span>  
  
|<span data-ttu-id="a815f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a815f-105">Method</span></span>|<span data-ttu-id="a815f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a815f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a815f-107">CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="a815f-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="a815f-108">Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.</span><span class="sxs-lookup"><span data-stu-id="a815f-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="a815f-109">DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="a815f-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="a815f-110">Fordert an, dass die CLR einen Iterator zerstört, der durch einen `CreateRWLockOwnerIterator`aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a815f-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="a815f-111">GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="a815f-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="a815f-112">Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.</span><span class="sxs-lookup"><span data-stu-id="a815f-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="a815f-113">GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="a815f-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="a815f-114">Ruft die nächste Aufgabe ab, die auf die aktuelle Lese-/Schreibsperre wartet.</span><span class="sxs-lookup"><span data-stu-id="a815f-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a815f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a815f-115">Requirements</span></span>  
 <span data-ttu-id="a815f-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a815f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a815f-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a815f-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a815f-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a815f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a815f-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a815f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a815f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a815f-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="a815f-121">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a815f-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="a815f-122">[Verwaltetes und nicht verwaltetes Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a815f-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="a815f-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a815f-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
