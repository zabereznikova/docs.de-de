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
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122082"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="58754-102">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58754-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="58754-103">Stellt Methoden bereit, mit denen der Common Language Runtime (CLR) den Thread Pool konfigurieren und Arbeitselemente in die Warteschlange für den Thread Pool einreihen kann.</span><span class="sxs-lookup"><span data-stu-id="58754-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58754-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="58754-104">Methods</span></span>  
  
|<span data-ttu-id="58754-105">Methode</span><span class="sxs-lookup"><span data-stu-id="58754-105">Method</span></span>|<span data-ttu-id="58754-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58754-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58754-107">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="58754-108">Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="58754-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="58754-109">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="58754-110">Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="58754-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="58754-111">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="58754-112">Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host in Erwartung von Anforderungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="58754-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="58754-113">QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="58754-114">Fügt eine Funktion zur Ausführung in die Warteschlange ein und stellt ein Objekt bereit, das von der Funktion zu verwendende Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="58754-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="58754-115">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="58754-116">Legt die maximale Anzahl von Threads fest, die der Host im Thread Pool verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="58754-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="58754-117">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="58754-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="58754-118">Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.</span><span class="sxs-lookup"><span data-stu-id="58754-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58754-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58754-119">Remarks</span></span>  
 <span data-ttu-id="58754-120">Der Host muss den Thread Pool nicht mithilfe der Werte konfigurieren, die in Aufrufen der Methoden `SetMaxThreads` und `SetMinThreads` angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="58754-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="58754-121">In diesem Fall sollte der Host einen HRESULT-Wert von E_NOTIMPL aus diesen Methoden zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="58754-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58754-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58754-122">Requirements</span></span>  
 <span data-ttu-id="58754-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58754-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58754-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="58754-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58754-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="58754-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58754-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58754-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58754-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58754-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="58754-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="58754-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
