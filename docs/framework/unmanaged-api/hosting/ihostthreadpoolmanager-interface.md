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
ms.openlocfilehash: b7fc0a271a9c62406d2942f387a5458e21211116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522725"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="4820b-102">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4820b-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="4820b-103">Enthält Methoden, die die common Language Runtime (CLR) zum Konfigurieren der Threadpool der Warteschleife hinzu und zum Arbeitsaufgaben an den Threadpool-Warteschlange zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4820b-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4820b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4820b-104">Methods</span></span>  
  
|<span data-ttu-id="4820b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-105">Method</span></span>|<span data-ttu-id="4820b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4820b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4820b-107">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="4820b-108">Ruft die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4820b-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="4820b-109">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="4820b-110">Ruft die maximale Anzahl von Threads, die der Host verwaltet, die gleichzeitig im Threadpool ab.</span><span class="sxs-lookup"><span data-stu-id="4820b-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="4820b-111">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="4820b-112">Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in der Erwartung Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="4820b-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="4820b-113">QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="4820b-114">Fügt eine Funktion für die Ausführung und stellt ein Objekt mit Daten, die von der Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4820b-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="4820b-115">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="4820b-116">Legt die maximale Anzahl von Threads, die der Host im Threadpool der Warteschleife hinzu verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="4820b-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="4820b-117">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="4820b-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="4820b-118">Legt die minimale Anzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="4820b-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4820b-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4820b-119">Remarks</span></span>  
 <span data-ttu-id="4820b-120">Der Host ist nicht erforderlich, so konfigurieren Sie den Threadpool mit den Werten, die in Aufrufen von angegeben die `SetMaxThreads` und `SetMinThreads` Methoden.</span><span class="sxs-lookup"><span data-stu-id="4820b-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="4820b-121">In diesem Fall sollte der Host einen HRESULT-Wert E_NOTIMPL von diesen Methoden zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4820b-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4820b-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4820b-122">Requirements</span></span>  
 <span data-ttu-id="4820b-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4820b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4820b-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4820b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4820b-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4820b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4820b-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4820b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4820b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4820b-127">See also</span></span>
- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="4820b-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4820b-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
