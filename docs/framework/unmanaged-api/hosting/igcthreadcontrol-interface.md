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
ms.openlocfilehash: 9296aedf24979624c3d7357a4d51be835716a16f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438027"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="83be3-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83be3-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="83be3-103">Stellt Methoden für die Einbeziehung in die Planung von Threads, die ansonsten für eine Garbagecollection blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="83be3-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83be3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="83be3-104">Methods</span></span>  
  
|<span data-ttu-id="83be3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="83be3-105">Method</span></span>|<span data-ttu-id="83be3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83be3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83be3-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="83be3-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="83be3-108">Benachrichtigt den Host an, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="83be3-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="83be3-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="83be3-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="83be3-110">Benachrichtigt den Host, dass die Common Language Runtime einen Thread anhalten für eine Garbagecollection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="83be3-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="83be3-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="83be3-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="83be3-112">Benachrichtigt den Host, der Thread, die den Aufruf zu blockieren, möglicherweise für eine Garbagecollection oder eine andere Unterbrechung ist.</span><span class="sxs-lookup"><span data-stu-id="83be3-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83be3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83be3-113">Requirements</span></span>  
 <span data-ttu-id="83be3-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83be3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83be3-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83be3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83be3-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="83be3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83be3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83be3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83be3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83be3-118">See Also</span></span>  
 [<span data-ttu-id="83be3-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="83be3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
