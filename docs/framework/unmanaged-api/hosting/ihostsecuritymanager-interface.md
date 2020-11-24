---
title: IHostSecurityManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 37f606a67bef79936c81b2a36f12a00d24bd82f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680533"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="04843-102">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04843-102">IHostSecurityManager Interface</span></span>

<span data-ttu-id="04843-103">Stellt Methoden bereit, mit denen der Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglicht und gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="04843-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04843-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="04843-104">Methods</span></span>  
  
|<span data-ttu-id="04843-105">Methode</span><span class="sxs-lookup"><span data-stu-id="04843-105">Method</span></span>|<span data-ttu-id="04843-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04843-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04843-107">GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="04843-108">Ruft den angeforderten [IHostSecurityContext](ihostsecuritycontext-interface.md) vom Host ab.</span><span class="sxs-lookup"><span data-stu-id="04843-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="04843-109">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="04843-110">Fordert die Ausführung von Code mit den Anmelde Informationen der aktuellen Benutzeridentität an.</span><span class="sxs-lookup"><span data-stu-id="04843-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="04843-111">OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="04843-112">Öffnet das freigegebene Zugriffs Token, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="04843-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="04843-113">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="04843-114">Beendet den Identitätswechsel der aktuellen Benutzeridentität und gibt das ursprüngliche Thread Token zurück.</span><span class="sxs-lookup"><span data-stu-id="04843-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="04843-115">SetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="04843-116">Legt den Sicherheitskontext für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="04843-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="04843-117">SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="04843-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="04843-118">Legt ein Handle für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="04843-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04843-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04843-119">Remarks</span></span>  

 <span data-ttu-id="04843-120">Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den Common Language Runtime (CLR) als auch durch den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="04843-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="04843-121">Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="04843-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="04843-122">`IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die CLR nicht transparent sind.</span><span class="sxs-lookup"><span data-stu-id="04843-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="04843-123">Die CLR verarbeitet den verwalteten Thread Kontext intern.</span><span class="sxs-lookup"><span data-stu-id="04843-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="04843-124">Die prozessspezifische Abfrage wird `IHostSecurityManager` in den folgenden Situationen abgefragt:</span><span class="sxs-lookup"><span data-stu-id="04843-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="04843-125">Im Finalizerthread während der Ausführung des Finalizers.</span><span class="sxs-lookup"><span data-stu-id="04843-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="04843-126">Während der Ausführung von Klassen-und Modulkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="04843-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="04843-127">Bei asynchronen Punkten im Arbeits Thread in Aufrufen der [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="04843-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="04843-128">Bei der Wartung von e/a-Abschlussports.</span><span class="sxs-lookup"><span data-stu-id="04843-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04843-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="04843-129">Requirements</span></span>  

 <span data-ttu-id="04843-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04843-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04843-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="04843-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04843-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="04843-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04843-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04843-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04843-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04843-134">See also</span></span>

- [<span data-ttu-id="04843-135">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04843-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="04843-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="04843-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
