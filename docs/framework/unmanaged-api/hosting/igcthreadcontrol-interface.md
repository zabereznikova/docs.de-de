---
title: IGCThreadControl-Schnittstelle
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
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: def6ae3c8bf8eea9cb135529e2b6e672b180e68c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="bb532-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb532-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="bb532-103">Stellt Methoden für die Einbeziehung in die Planung von Threads, die ansonsten für eine Garbagecollection blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="bb532-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb532-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bb532-104">Methods</span></span>  
  
|<span data-ttu-id="bb532-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bb532-105">Method</span></span>|<span data-ttu-id="bb532-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb532-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb532-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="bb532-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="bb532-108">Benachrichtigt den Host an, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="bb532-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="bb532-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="bb532-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="bb532-110">Benachrichtigt den Host, dass die Common Language Runtime einen Thread anhalten für eine Garbagecollection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="bb532-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="bb532-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="bb532-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="bb532-112">Benachrichtigt den Host, der Thread, die den Aufruf zu blockieren, möglicherweise für eine Garbagecollection oder eine andere Unterbrechung ist.</span><span class="sxs-lookup"><span data-stu-id="bb532-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb532-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb532-113">Requirements</span></span>  
 <span data-ttu-id="bb532-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb532-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb532-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb532-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb532-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb532-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb532-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb532-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb532-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb532-118">See Also</span></span>  
 [<span data-ttu-id="bb532-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb532-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
