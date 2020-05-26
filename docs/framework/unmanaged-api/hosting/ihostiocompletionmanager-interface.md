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
ms.openlocfilehash: 90675d9be71342efa903767abbf63102b40a2c35
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804686"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="f3738-102">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3738-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="f3738-103">Stellt Methoden bereit, die dem Common Language Runtime (CLR) die Interaktion mit e/a-Abschlussports ermöglichen, die vom Host bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f3738-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3738-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3738-104">Methods</span></span>  
  
|<span data-ttu-id="f3738-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-105">Method</span></span>|<span data-ttu-id="f3738-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f3738-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3738-107">Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-107">Bind Method</span></span>](ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="f3738-108">Bindet ein Handle an einen e/a-Abschlussport.</span><span class="sxs-lookup"><span data-stu-id="f3738-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="f3738-109">CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-109">CloseIoCompletionPort Method</span></span>](ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="f3738-110">Schließt einen Port, der durch einen früheren-Aufrufsatz erstellt wurde `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="f3738-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="f3738-111">CreateIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-111">CreateIoCompletionPort Method</span></span>](ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="f3738-112">Fordert an, dass der Host einen neuen e/a-Abschlussport erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3738-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="f3738-113">GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-113">GetAvailableThreads Method</span></span>](ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="f3738-114">Ruft die Anzahl der e/a-Abschluss Threads ab, die derzeit keine Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f3738-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="f3738-115">GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-115">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="f3738-116">Ruft die Größe aller benutzerdefinierten Daten ab, die der Host an e/a-Anforderungen anfügen soll.</span><span class="sxs-lookup"><span data-stu-id="f3738-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="f3738-117">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-117">GetMaxThreads Method</span></span>](ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="f3738-118">Ruft die maximale Anzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen in hohem Maß abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f3738-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="f3738-119">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-119">GetMinThreads Method</span></span>](ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="f3738-120">Ruft die Mindestanzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f3738-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="f3738-121">InitializeHostOverlapped-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-121">InitializeHostOverlapped Method</span></span>](ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="f3738-122">Bietet dem Host die Möglichkeit, benutzerdefinierte Daten zu einer e/a-Anforderung zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f3738-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="f3738-123">SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="f3738-124">Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) -Instanz bereit, die von der CLR implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f3738-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="f3738-125">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-125">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="f3738-126">Legt die maximale Anzahl von Threads fest, die der Host Dienst-e/a-Anforderungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f3738-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="f3738-127">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f3738-127">SetMinThreads Method</span></span>](ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="f3738-128">Legt die Mindestanzahl von Threads fest, die der Host für die e/a-Vervollständigung in hohem Maß beachten soll.</span><span class="sxs-lookup"><span data-stu-id="f3738-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3738-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3738-129">Remarks</span></span>  
 <span data-ttu-id="f3738-130">`IHostIoCompletionManager`entspricht der `ICLRIoCompletionManager` von der CLR implementierten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f3738-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="f3738-131">Die CLR ruft die Methoden von `IHostIoCompletionManager` auf, um Handles an die vom Host bereitgestellten Ports zu binden, und der Host ruft die Methoden von `ICLRIoCompletionManager` auf, um den Abschluss von e/a-Anforderungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="f3738-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3738-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3738-132">Requirements</span></span>  
 <span data-ttu-id="f3738-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3738-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3738-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f3738-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3738-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f3738-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3738-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3738-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3738-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3738-137">See also</span></span>

- [<span data-ttu-id="f3738-138">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3738-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
