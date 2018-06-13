---
title: IHostThreadPoolManager-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92097cdf735630f3537296f188bd83ea8162add2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441130"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="4f225-102">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f225-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="4f225-103">Enthält Methoden, die die common Language Runtime (CLR) so konfigurieren Sie den Pool und an die Warteschlange Arbeitsaufgaben an den Threadpool zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4f225-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f225-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f225-104">Methods</span></span>  
  
|<span data-ttu-id="4f225-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-105">Method</span></span>|<span data-ttu-id="4f225-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f225-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f225-107">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="4f225-108">Ruft die Anzahl der Threads im Threadpool, der von Arbeitselementen derzeit nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4f225-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="4f225-109">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="4f225-110">Ruft die maximale Anzahl von Threads, die der Host gleichzeitig im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="4f225-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="4f225-111">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="4f225-112">Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in Vorwegnahme Ihrer Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4f225-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="4f225-113">QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="4f225-114">Fügt eine Funktion für die Ausführung der Warteschlange hinzu und stellt ein Objekt mit den Daten, die von der Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f225-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="4f225-115">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="4f225-116">Legt die maximale Anzahl von Threads, die der Host im Threadpool verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="4f225-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="4f225-117">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4f225-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="4f225-118">Legt die Mindestanzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="4f225-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f225-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f225-119">Remarks</span></span>  
 <span data-ttu-id="4f225-120">Der Host ist nicht erforderlich, so konfigurieren Sie den Threadpool mithilfe der Werte, angegeben in Aufrufen an die `SetMaxThreads` und `SetMinThreads` Methoden.</span><span class="sxs-lookup"><span data-stu-id="4f225-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="4f225-121">In diesem Fall sollte der Host einen HRESULT-Wert E_NOTIMPL von diesen Methoden zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4f225-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f225-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f225-122">Requirements</span></span>  
 <span data-ttu-id="4f225-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f225-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f225-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f225-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f225-125">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4f225-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f225-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f225-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f225-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f225-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="4f225-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f225-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
