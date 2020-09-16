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
ms.openlocfilehash: b0b9c0b7d178557806a9ab2893bff2d34dc408ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557735"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="8f787-102">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f787-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="8f787-103">Definiert Methoden, die es dem Host ermöglichen, Informationen zu angeforderten Tasks zu erhalten und Deadlocks in der Synchronisierungs Implementierung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="8f787-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f787-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8f787-104">Methods</span></span>  
  
|<span data-ttu-id="8f787-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8f787-105">Method</span></span>|<span data-ttu-id="8f787-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f787-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f787-107">CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="8f787-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="8f787-108">Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.</span><span class="sxs-lookup"><span data-stu-id="8f787-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="8f787-109">DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="8f787-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="8f787-110">Fordert an, dass die CLR einen Iterator zerstört, der durch einen-Rückruf erstellt wurde `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="8f787-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="8f787-111">GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="8f787-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="8f787-112">Ruft die Aufgabe ab, die den angegebenen Monitor besitzt.</span><span class="sxs-lookup"><span data-stu-id="8f787-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="8f787-113">GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="8f787-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="8f787-114">Ruft die nächste Aufgabe ab, die auf die aktuelle Lese-/Schreibsperre wartet.</span><span class="sxs-lookup"><span data-stu-id="8f787-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f787-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f787-115">Requirements</span></span>  
 <span data-ttu-id="8f787-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f787-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f787-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8f787-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f787-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f787-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f787-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f787-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f787-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f787-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="8f787-121">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f787-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="8f787-122">[Managed and Unmanaged Threading (Verwaltetes und nicht verwaltetes Threading)](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f787-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="8f787-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8f787-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
