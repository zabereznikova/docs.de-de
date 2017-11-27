---
title: IHostSecurityManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="b9ba0-102">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9ba0-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="b9ba0-103">Enthält Methoden, die Zugriff auf und die Kontrolle über den Sicherheitskontext des gerade ausgeführten Thread zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9ba0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b9ba0-104">Methods</span></span>  
  
|<span data-ttu-id="b9ba0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-105">Method</span></span>|<span data-ttu-id="b9ba0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9ba0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9ba0-107">GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="b9ba0-108">Ruft den angeforderten [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="b9ba0-109">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="b9ba0-110">Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="b9ba0-111">OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="b9ba0-112">Öffnet das freigegebene Zugriffstoken, das dem aktuellen Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="b9ba0-113">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="b9ba0-114">Beendet den Identitätswechsel der Identität des aktuellen Benutzers und der ursprüngliche Threadtoken zurück.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="b9ba0-115">SetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="b9ba0-116">Legt den Sicherheitskontext für den gerade ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="b9ba0-117">SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b9ba0-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="b9ba0-118">Legt einen Handle für den gerade ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9ba0-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9ba0-119">Remarks</span></span>  
 <span data-ttu-id="b9ba0-120">Ein Host kann alle Codezugriff auf Threadtoken von der common Language Runtime (CLR) und den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="b9ba0-121">Sie können auch sicherstellen, dass vollständige Kontextinformationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="b9ba0-122">`IHostSecurityContext`kapselt diese Sicherheitskontextinformationen, die für die CLR nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="b9ba0-123">Die CLR behandelt verwalteten Threadkontext intern.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="b9ba0-124">Anschließend fragt es die prozessspezifische `IHostSecurityManager` in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="b9ba0-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="b9ba0-125">Der Finalizer-Thread, während der Finalizerausführung.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="b9ba0-126">Während der Ausführung der Klasse und Module-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="b9ba0-127">Asynchrone Zeitpunkten in der Arbeitsthread in Aufrufen an die [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="b9ba0-128">Im Wartungsmodus von e/a-Abschlussports.</span><span class="sxs-lookup"><span data-stu-id="b9ba0-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ba0-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9ba0-129">Requirements</span></span>  
 <span data-ttu-id="b9ba0-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ba0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ba0-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9ba0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9ba0-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b9ba0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9ba0-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ba0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ba0-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9ba0-134">See Also</span></span>  
 [<span data-ttu-id="b9ba0-135">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9ba0-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="b9ba0-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b9ba0-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
