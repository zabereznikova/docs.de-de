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
ms.openlocfilehash: 238b054d240437df64a83a9c4daad34d4bd5d36a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228878"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="41e67-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e67-102">IHostGCManager Interface</span></span>
<span data-ttu-id="41e67-103">Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der common Language Runtime (CLR) zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="41e67-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="41e67-104">Member</span><span class="sxs-lookup"><span data-stu-id="41e67-104">Members</span></span>  
  
|<span data-ttu-id="41e67-105">Member</span><span class="sxs-lookup"><span data-stu-id="41e67-105">Member</span></span>|<span data-ttu-id="41e67-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41e67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41e67-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="41e67-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="41e67-108">Benachrichtigt den Host, dass die CLR die Ausführung von Aufgaben in Threads fortgesetzt wird, die für eine Garbagecollection unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="41e67-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="41e67-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="41e67-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="41e67-110">Benachrichtigt den Host an, dass die CLR die Ausführung von Aufgaben für eine Garbagecollection angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="41e67-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="41e67-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="41e67-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="41e67-112">Benachrichtigt den Host, der der Thread aus dem Aufruf der Methode wurde zu, um für eine Garbagecollection zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="41e67-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41e67-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41e67-113">Requirements</span></span>  
 <span data-ttu-id="41e67-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41e67-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e67-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="41e67-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41e67-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="41e67-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="41e67-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="41e67-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41e67-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41e67-118">See also</span></span>

- [<span data-ttu-id="41e67-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e67-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="41e67-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e67-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="41e67-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e67-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="41e67-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e67-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="41e67-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41e67-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
