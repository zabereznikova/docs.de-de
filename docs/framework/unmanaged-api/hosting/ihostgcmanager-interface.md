---
title: IHostGCManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: eb7e52b5237d4341c27b8c167249dc2614168679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729523"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="ead33-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead33-102">IHostGCManager Interface</span></span>

<span data-ttu-id="ead33-103">Stellt Methoden bereit, die den Host von Ereignissen in dem Garbage Collection Mechanismus benachrichtigen, der vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ead33-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="ead33-104">Member</span><span class="sxs-lookup"><span data-stu-id="ead33-104">Members</span></span>  
  
|<span data-ttu-id="ead33-105">Member</span><span class="sxs-lookup"><span data-stu-id="ead33-105">Member</span></span>|<span data-ttu-id="ead33-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ead33-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ead33-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="ead33-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="ead33-108">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="ead33-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="ead33-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="ead33-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="ead33-110">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks unterteilt, um eine Garbage Collection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ead33-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="ead33-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="ead33-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="ead33-112">Benachrichtigt den Host, dass der Thread, von dem der Methoden aufrufging, für eine Garbage Collection blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ead33-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ead33-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ead33-113">Requirements</span></span>  

 <span data-ttu-id="ead33-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ead33-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead33-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ead33-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ead33-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ead33-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ead33-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead33-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead33-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ead33-118">See also</span></span>

- [<span data-ttu-id="ead33-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead33-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ead33-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead33-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ead33-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead33-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ead33-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead33-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="ead33-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ead33-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
