---
title: ICLRTask2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="408f6-102">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="408f6-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="408f6-103">Stellt die Funktionalität von der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle; darüber hinaus bietet Methoden, die es ermöglichen, Thread-Abbrüche um für den aktuellen Thread verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="408f6-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="408f6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="408f6-104">Methods</span></span>  
  
|<span data-ttu-id="408f6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="408f6-105">Method</span></span>|<span data-ttu-id="408f6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="408f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="408f6-107">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="408f6-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="408f6-108">Neuer Thread Verzögerungen Abbrechen Anforderungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="408f6-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="408f6-109">EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="408f6-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="408f6-110">Ermöglicht, dass neue oder ausstehende Thread Abort Anforderungen zu Thread führt bricht ab, für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="408f6-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="408f6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="408f6-111">Remarks</span></span>  
 <span data-ttu-id="408f6-112">Die `ICLRTask2` Schnittstelle erbt die `ICLRTask` Schnittstelle und fügt Methoden, mit denen den Host zu verzögern, Threadabbrüche, um einen Bereich von Code zu schützen, die nicht fehlschlagen darf.</span><span class="sxs-lookup"><span data-stu-id="408f6-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="408f6-113">Aufrufen von `BeginPreventAsyncAbort` erhöht den Zähler Verzögerung Threadabbruchs für den aktuellen Thread, und der Aufruf `EndPreventAsyncAbort` verringert es.</span><span class="sxs-lookup"><span data-stu-id="408f6-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="408f6-114">Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können geschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="408f6-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="408f6-115">Solange der Leistungsindikator größer als 0 (null) ist, werden Threadabbrüche für den aktuellen Thread verzögert.</span><span class="sxs-lookup"><span data-stu-id="408f6-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="408f6-116">Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` werden nicht paarweise zugeordnet, es ist möglich, einen Status erreichen, in welchem Thread Threadabbrüche für den aktuellen Thread nicht übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="408f6-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="408f6-117">Die Verzögerung wird für einen Thread, der selbst abbricht, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="408f6-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="408f6-118">Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="408f6-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="408f6-119">Missbrauch dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="408f6-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="408f6-120">Beispielsweise Aufrufen `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn der virtuellen Computer zuvor erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="408f6-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="408f6-121">Auf ähnliche Weise wird der interne Zähler auf Überläufe nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="408f6-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="408f6-122">Wenn er ganzzahlige Limit überschreitet, da er vom Host und dem virtuellen Computer erhöht wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="408f6-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="408f6-123">Für Informationen zu Elementen geerbt `ICLRTask` und zu anderen Verwendungsmöglichkeiten dieser Schnittstelle finden Sie unter der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="408f6-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="408f6-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="408f6-124">Requirements</span></span>  
 <span data-ttu-id="408f6-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="408f6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="408f6-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="408f6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="408f6-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="408f6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="408f6-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="408f6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408f6-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="408f6-129">See Also</span></span>  
 [<span data-ttu-id="408f6-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="408f6-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="408f6-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="408f6-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="408f6-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="408f6-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="408f6-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="408f6-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="408f6-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="408f6-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
