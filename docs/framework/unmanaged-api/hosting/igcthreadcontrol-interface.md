---
title: IGCThreadControl-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a053dba8f5fb8f4144968e08b6c65412f510193
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727494"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="1ba7e-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ba7e-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="1ba7e-103">Stellt Methoden für die Teilnahme an der Planung von Threads, die für eine Garbagecollection andernfalls blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="1ba7e-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ba7e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ba7e-104">Methods</span></span>  
  
|<span data-ttu-id="1ba7e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1ba7e-105">Method</span></span>|<span data-ttu-id="1ba7e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ba7e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ba7e-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="1ba7e-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="1ba7e-108">Benachrichtigt den Host, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1ba7e-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="1ba7e-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="1ba7e-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="1ba7e-110">Benachrichtigt den Host, dass die Laufzeit eine Threadunterbrechung für eine Garbagecollection oder einer anderen Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="1ba7e-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="1ba7e-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="1ba7e-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="1ba7e-112">Benachrichtigt den Host an, dass der Thread, der den Aufruf zu blockieren, z. B. für eine Garbagecollection oder einer anderen Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="1ba7e-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ba7e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ba7e-113">Requirements</span></span>  
 <span data-ttu-id="1ba7e-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ba7e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba7e-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ba7e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ba7e-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ba7e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ba7e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba7e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba7e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ba7e-118">See also</span></span>
- [<span data-ttu-id="1ba7e-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ba7e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
