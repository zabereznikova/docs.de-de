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
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805130"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="4aaf3-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4aaf3-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="4aaf3-103">Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="4aaf3-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4aaf3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4aaf3-104">Methods</span></span>  
  
|<span data-ttu-id="4aaf3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4aaf3-105">Method</span></span>|<span data-ttu-id="4aaf3-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4aaf3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4aaf3-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="4aaf3-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="4aaf3-108">Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="4aaf3-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="4aaf3-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="4aaf3-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="4aaf3-110">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="4aaf3-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="4aaf3-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="4aaf3-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="4aaf3-112">Benachrichtigt den Host, dass der Thread, der den-anfordert, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="4aaf3-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4aaf3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4aaf3-113">Requirements</span></span>  
 <span data-ttu-id="4aaf3-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aaf3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aaf3-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4aaf3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4aaf3-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4aaf3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4aaf3-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aaf3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aaf3-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4aaf3-118">See also</span></span>

- [<span data-ttu-id="4aaf3-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4aaf3-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
