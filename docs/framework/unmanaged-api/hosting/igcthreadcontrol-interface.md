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
ms.openlocfilehash: 02facbb0ff1c0f8978d4f4f720ab370f70f07fe2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721685"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="e8b99-102">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8b99-102">IGCThreadControl Interface</span></span>

<span data-ttu-id="e8b99-103">Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8b99-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8b99-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8b99-104">Methods</span></span>  
  
|<span data-ttu-id="e8b99-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e8b99-105">Method</span></span>|<span data-ttu-id="e8b99-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8b99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8b99-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b99-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="e8b99-108">Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="e8b99-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="e8b99-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b99-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="e8b99-110">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="e8b99-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="e8b99-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b99-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="e8b99-112">Benachrichtigt den Host, dass der Thread, der den-anfordert, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="e8b99-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8b99-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e8b99-113">Requirements</span></span>  

 <span data-ttu-id="e8b99-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b99-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b99-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e8b99-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8b99-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8b99-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8b99-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b99-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b99-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8b99-118">See also</span></span>

- [<span data-ttu-id="e8b99-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8b99-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
