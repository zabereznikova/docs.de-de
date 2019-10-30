---
title: ICLRTask2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124523"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="5fe15-102">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fe15-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="5fe15-103">Stellt die gesamte Funktionalität der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Schnittstelle bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.</span><span class="sxs-lookup"><span data-stu-id="5fe15-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fe15-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5fe15-104">Methods</span></span>  
  
|<span data-ttu-id="5fe15-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5fe15-105">Method</span></span>|<span data-ttu-id="5fe15-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fe15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fe15-107">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="5fe15-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="5fe15-108">Verzögert neue Thread Abbruch Anforderungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="5fe15-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="5fe15-109">EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="5fe15-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="5fe15-110">Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="5fe15-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fe15-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fe15-111">Remarks</span></span>  
 <span data-ttu-id="5fe15-112">Die `ICLRTask2`-Schnittstelle erbt die `ICLRTask`-Schnittstelle und fügt Methoden hinzu, mit denen der Host Thread Abbrüche verzögern kann, um einen Code Bereich zu schützen, der nicht fehlschlagen darf.</span><span class="sxs-lookup"><span data-stu-id="5fe15-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="5fe15-113">Durch Aufrufen von `BeginPreventAsyncAbort` wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread erhöht, und der Aufruf von `EndPreventAsyncAbort` Dekremente ihn.</span><span class="sxs-lookup"><span data-stu-id="5fe15-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="5fe15-114">Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="5fe15-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="5fe15-115">Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.</span><span class="sxs-lookup"><span data-stu-id="5fe15-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="5fe15-116">Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` nicht gekoppelt sind, ist es möglich, einen Zustand zu erreichen, in dem Thread Abbrüche nicht an den aktuellen Thread übermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="5fe15-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="5fe15-117">Die Verzögerung wird für einen Thread, der sich selbst abbricht, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5fe15-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="5fe15-118">Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fe15-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="5fe15-119">Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen.</span><span class="sxs-lookup"><span data-stu-id="5fe15-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="5fe15-120">Wenn Sie z. b. `EndPreventAsyncAbort` aufrufen, ohne zuerst `BeginPreventAsyncAbort` aufrufen, können Sie den-Wert auf NULL festlegen, wenn der virtuelle Computer ihn zuvor erhöht hat.</span><span class="sxs-lookup"><span data-stu-id="5fe15-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="5fe15-121">Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft.</span><span class="sxs-lookup"><span data-stu-id="5fe15-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="5fe15-122">Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="5fe15-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="5fe15-123">Informationen zu Membern, die von `ICLRTask` geerbt werden, sowie zu den anderen Verwendungsmöglichkeiten dieser Schnittstelle finden Sie in der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5fe15-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe15-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fe15-124">Requirements</span></span>  
 <span data-ttu-id="5fe15-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe15-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe15-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5fe15-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5fe15-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5fe15-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fe15-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe15-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe15-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fe15-129">See also</span></span>

- [<span data-ttu-id="5fe15-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fe15-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5fe15-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fe15-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5fe15-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fe15-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5fe15-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fe15-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="5fe15-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fe15-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
