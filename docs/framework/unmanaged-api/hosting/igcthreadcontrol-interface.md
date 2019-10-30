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
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134804"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="99cf0-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99cf0-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="99cf0-103">Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="99cf0-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99cf0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="99cf0-104">Methods</span></span>  
  
|<span data-ttu-id="99cf0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="99cf0-105">Method</span></span>|<span data-ttu-id="99cf0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99cf0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99cf0-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="99cf0-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="99cf0-108">Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="99cf0-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="99cf0-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="99cf0-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="99cf0-110">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="99cf0-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="99cf0-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="99cf0-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="99cf0-112">Benachrichtigt den Host, dass der Thread, der den-anfordert, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="99cf0-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99cf0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99cf0-113">Requirements</span></span>  
 <span data-ttu-id="99cf0-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99cf0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99cf0-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="99cf0-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99cf0-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99cf0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99cf0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99cf0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99cf0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99cf0-118">See also</span></span>

- [<span data-ttu-id="99cf0-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99cf0-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
