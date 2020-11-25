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
ms.openlocfilehash: b6625b0ef4dc3de4067514a0b39849c7a958d5c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730759"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="48d25-102">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48d25-102">IHostThreadPoolManager Interface</span></span>

<span data-ttu-id="48d25-103">Stellt Methoden bereit, mit denen der Common Language Runtime (CLR) den Thread Pool konfigurieren und Arbeitselemente in die Warteschlange für den Thread Pool einreihen kann.</span><span class="sxs-lookup"><span data-stu-id="48d25-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48d25-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="48d25-104">Methods</span></span>  
  
|<span data-ttu-id="48d25-105">Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-105">Method</span></span>|<span data-ttu-id="48d25-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48d25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48d25-107">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-107">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="48d25-108">Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48d25-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="48d25-109">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-109">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="48d25-110">Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="48d25-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="48d25-111">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-111">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="48d25-112">Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host in Erwartung von Anforderungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="48d25-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="48d25-113">QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-113">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="48d25-114">Fügt eine Funktion zur Ausführung in die Warteschlange ein und stellt ein Objekt bereit, das von der Funktion zu verwendende Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="48d25-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="48d25-115">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-115">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="48d25-116">Legt die maximale Anzahl von Threads fest, die der Host im Thread Pool verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="48d25-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="48d25-117">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="48d25-117">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="48d25-118">Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.</span><span class="sxs-lookup"><span data-stu-id="48d25-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48d25-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48d25-119">Remarks</span></span>  

 <span data-ttu-id="48d25-120">Der Host muss den Thread Pool nicht mit den Werten konfigurieren, die in Aufrufen der `SetMaxThreads` -Methode und der-Methode angegeben sind `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="48d25-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="48d25-121">In diesem Fall sollte der Host den HRESULT-Wert E_NOTIMPL aus diesen Methoden zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="48d25-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d25-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="48d25-122">Requirements</span></span>  

 <span data-ttu-id="48d25-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d25-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d25-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="48d25-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48d25-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48d25-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48d25-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d25-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d25-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48d25-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="48d25-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="48d25-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
