---
title: IHostIoCompletionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197268"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="466af-102">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="466af-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="466af-103">Enthält Methoden, die die common Language Runtime (CLR) für die Interaktion mit e/a-Abschlussports, die vom Host zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="466af-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="466af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="466af-104">Methods</span></span>  
  
|<span data-ttu-id="466af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="466af-105">Method</span></span>|<span data-ttu-id="466af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="466af-107">Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="466af-108">Wird ein Handle an einen e/a-Abschlussanschluss gebunden.</span><span class="sxs-lookup"><span data-stu-id="466af-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="466af-109">CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="466af-110">Schließt einen Port, der durch einen früheren Aufruf von erstellten `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="466af-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="466af-111">CreateIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="466af-112">Fordert an, dass der Host eine neue e/a-Abschlussport zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="466af-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="466af-113">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="466af-114">Ruft die Anzahl der e/a-Abschlussthreads, die derzeit keine Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="466af-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="466af-115">GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="466af-116">Ruft die Größe der benutzerdefinierten Daten, die der Host möchte an e/a-Anforderungen angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="466af-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="466af-117">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="466af-118">Ruft die maximale Anzahl von Threads, die der Host-Manual kann e/a-Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="466af-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="466af-119">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="466af-120">Ruft die minimale Anzahl von Threads, die vom Host bereitgestellten e/a-Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="466af-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="466af-121">InitializeHostOverlapped-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="466af-122">Stellt den Host Möglichkeit, benutzerdefinierte Daten über eine e/a-Anforderung zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="466af-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="466af-123">SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="466af-124">Bietet einen Schnittstellenzeiger auf den Host ein [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) -Instanz, von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="466af-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="466af-125">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="466af-126">Legt die maximale Anzahl von Threads, die der Host-Bereitstellung e/a-Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="466af-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="466af-127">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="466af-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="466af-128">Legt die minimale Anzahl von Threads, die der Host-Manual sollte auf e/a-Abschluss fest.</span><span class="sxs-lookup"><span data-stu-id="466af-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466af-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="466af-129">Remarks</span></span>  
 <span data-ttu-id="466af-130">`IHostIoCompletionManager` entspricht der `ICLRIoCompletionManager` Schnittstelle, die von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="466af-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="466af-131">Die CLR ruft die Methoden der `IHostIoCompletionManager` Handles an den Ports binden, der der Host und der Host Ruft die Methoden der `ICLRIoCompletionManager` melden den Abschluss von e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="466af-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="466af-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="466af-132">Requirements</span></span>  
 <span data-ttu-id="466af-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="466af-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466af-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="466af-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="466af-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="466af-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="466af-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466af-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466af-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="466af-137">See also</span></span>

- [<span data-ttu-id="466af-138">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="466af-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
