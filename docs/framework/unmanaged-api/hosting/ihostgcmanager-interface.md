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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4eac8abede82915386abc19c4c8389932451df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440375"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="fb563-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb563-102">IHostGCManager Interface</span></span>
<span data-ttu-id="fb563-103">Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der common Language Runtime (CLR) zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="fb563-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="fb563-104">Member</span><span class="sxs-lookup"><span data-stu-id="fb563-104">Members</span></span>  
  
|<span data-ttu-id="fb563-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb563-105">Member</span></span>|<span data-ttu-id="fb563-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb563-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb563-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="fb563-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="fb563-108">Benachrichtigt den Host, dass die CLR die Ausführung von Aufgaben in Threads fortgesetzt wird, die für eine Garbagecollection unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="fb563-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="fb563-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="fb563-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="fb563-110">Benachrichtigt den Host, dass die CLR unterbricht die Ausführung von Aufgaben auf, um eine Garbagecollection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb563-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="fb563-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="fb563-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="fb563-112">Benachrichtigt den Host, der Thread aus dem Aufruf der Methode eingegangen ist, bald für eine Garbagecollection zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="fb563-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb563-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb563-113">Requirements</span></span>  
 <span data-ttu-id="fb563-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb563-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb563-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb563-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb563-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fb563-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb563-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb563-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb563-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb563-118">See Also</span></span>  
 [<span data-ttu-id="fb563-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb563-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fb563-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb563-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fb563-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb563-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fb563-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb563-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="fb563-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fb563-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
