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
ms.openlocfilehash: 6f7158bcac7ad22647104e2041da959285d2be8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130478"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="8ff29-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ff29-102">IHostGCManager Interface</span></span>
<span data-ttu-id="8ff29-103">Stellt Methoden bereit, die den Host von Ereignissen in dem Garbage Collection Mechanismus benachrichtigen, der vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ff29-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="8ff29-104">Member</span><span class="sxs-lookup"><span data-stu-id="8ff29-104">Members</span></span>  
  
|<span data-ttu-id="8ff29-105">Member</span><span class="sxs-lookup"><span data-stu-id="8ff29-105">Member</span></span>|<span data-ttu-id="8ff29-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ff29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ff29-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="8ff29-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="8ff29-108">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="8ff29-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="8ff29-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="8ff29-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="8ff29-110">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks unterteilt, um eine Garbage Collection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8ff29-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="8ff29-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="8ff29-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="8ff29-112">Benachrichtigt den Host, dass der Thread, von dem der Methoden aufrufging, für eine Garbage Collection blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ff29-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ff29-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ff29-113">Requirements</span></span>  
 <span data-ttu-id="8ff29-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff29-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff29-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8ff29-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ff29-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ff29-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ff29-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff29-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff29-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ff29-118">See also</span></span>

- [<span data-ttu-id="8ff29-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ff29-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8ff29-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ff29-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8ff29-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ff29-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8ff29-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ff29-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8ff29-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ff29-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
