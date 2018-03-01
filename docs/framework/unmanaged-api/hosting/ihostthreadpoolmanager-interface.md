---
title: IHostThreadPoolManager-Schnittstelle
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
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1cd58c53deec0a895ae6f67cccf26d2c8c2530be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="43654-102">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43654-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="43654-103">Enthält Methoden, die die common Language Runtime (CLR) so konfigurieren Sie den Pool und an die Warteschlange Arbeitsaufgaben an den Threadpool zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="43654-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43654-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="43654-104">Methods</span></span>  
  
|<span data-ttu-id="43654-105">Methode</span><span class="sxs-lookup"><span data-stu-id="43654-105">Method</span></span>|<span data-ttu-id="43654-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43654-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43654-107">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="43654-108">Ruft die Anzahl der Threads im Threadpool, der von Arbeitselementen derzeit nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43654-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="43654-109">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="43654-110">Ruft die maximale Anzahl von Threads, die der Host gleichzeitig im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="43654-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="43654-111">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="43654-112">Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in Vorwegnahme Ihrer Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="43654-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="43654-113">QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="43654-114">Fügt eine Funktion für die Ausführung der Warteschlange hinzu und stellt ein Objekt mit den Daten, die von der Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43654-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="43654-115">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="43654-116">Legt die maximale Anzahl von Threads, die der Host im Threadpool verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="43654-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="43654-117">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="43654-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="43654-118">Legt die Mindestanzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="43654-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43654-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43654-119">Remarks</span></span>  
 <span data-ttu-id="43654-120">Der Host ist nicht erforderlich, so konfigurieren Sie den Threadpool mithilfe der Werte, angegeben in Aufrufen an die `SetMaxThreads` und `SetMinThreads` Methoden.</span><span class="sxs-lookup"><span data-stu-id="43654-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="43654-121">In diesem Fall sollte der Host einen HRESULT-Wert E_NOTIMPL von diesen Methoden zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="43654-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43654-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43654-122">Requirements</span></span>  
 <span data-ttu-id="43654-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43654-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43654-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43654-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43654-125">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43654-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43654-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43654-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43654-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43654-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="43654-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="43654-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
