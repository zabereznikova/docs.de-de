---
title: IHostGCManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7452f49df6970bf2ca49781f6a38874186bec64f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="20452-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20452-102">IHostGCManager Interface</span></span>
<span data-ttu-id="20452-103">Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der common Language Runtime (CLR) zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="20452-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="20452-104">Member</span><span class="sxs-lookup"><span data-stu-id="20452-104">Members</span></span>  
  
|<span data-ttu-id="20452-105">Member</span><span class="sxs-lookup"><span data-stu-id="20452-105">Member</span></span>|<span data-ttu-id="20452-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20452-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20452-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="20452-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="20452-108">Benachrichtigt den Host, dass die CLR die Ausführung von Aufgaben in Threads fortgesetzt wird, die für eine Garbagecollection unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="20452-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="20452-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="20452-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="20452-110">Benachrichtigt den Host, dass die CLR unterbricht die Ausführung von Aufgaben auf, um eine Garbagecollection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="20452-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="20452-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="20452-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="20452-112">Benachrichtigt den Host, der Thread aus dem Aufruf der Methode eingegangen ist, bald für eine Garbagecollection zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="20452-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20452-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20452-113">Requirements</span></span>  
 <span data-ttu-id="20452-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20452-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20452-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20452-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20452-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20452-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20452-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20452-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20452-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20452-118">See Also</span></span>  
 [<span data-ttu-id="20452-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20452-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="20452-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20452-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="20452-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20452-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="20452-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20452-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="20452-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="20452-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
