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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45379fe8640ef7e7b3917bac8d10ca956d75ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957585"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="db1eb-102">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db1eb-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="db1eb-103">Enthält Methoden, die Zugriff auf und Kontrolle über den Sicherheitskontext des gerade ausgeführten Threads zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db1eb-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db1eb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="db1eb-104">Methods</span></span>  
  
|<span data-ttu-id="db1eb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-105">Method</span></span>|<span data-ttu-id="db1eb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db1eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db1eb-107">GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="db1eb-108">Ruft die angeforderte [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host.</span><span class="sxs-lookup"><span data-stu-id="db1eb-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="db1eb-109">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="db1eb-110">Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db1eb-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="db1eb-111">OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="db1eb-112">Öffnet das discretionary Access Control-Token, das den aktuellen Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="db1eb-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="db1eb-113">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="db1eb-114">Beendet den Identitätswechsel der Identität des aktuellen Benutzers und gibt das Threadtoken der ursprüngliche zurück.</span><span class="sxs-lookup"><span data-stu-id="db1eb-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="db1eb-115">SetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="db1eb-116">Legt den Sicherheitskontext für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="db1eb-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="db1eb-117">SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="db1eb-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="db1eb-118">Legt einen Handle für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="db1eb-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db1eb-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db1eb-119">Remarks</span></span>  
 <span data-ttu-id="db1eb-120">Ein Host kann alle Codezugriff auf Threadtoken durch die common Language Runtime (CLR) und den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="db1eb-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="db1eb-121">Sie können auch sicherstellen, dass vollständige Informationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="db1eb-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="db1eb-122">`IHostSecurityContext` kapselt dieses Sicherheitskontextinformationen, die für die CLR nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="db1eb-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="db1eb-123">Die CLR behandelt die intern verwalteten Thread-Kontext.</span><span class="sxs-lookup"><span data-stu-id="db1eb-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="db1eb-124">Die Prozess-spezifischen Abfragen `IHostSecurityManager` in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="db1eb-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="db1eb-125">Der Finalizer-Thread, während der Finalizerausführung.</span><span class="sxs-lookup"><span data-stu-id="db1eb-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="db1eb-126">Während der Ausführung der Klasse "und"-Modul-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="db1eb-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="db1eb-127">Auf den Arbeitsthread, in Aufrufen von asynchronen Zeitpunkten der [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="db1eb-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="db1eb-128">Im Wartungsmodus von e/a-Abschlussports.</span><span class="sxs-lookup"><span data-stu-id="db1eb-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1eb-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db1eb-129">Requirements</span></span>  
 <span data-ttu-id="db1eb-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db1eb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1eb-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db1eb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db1eb-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db1eb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db1eb-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1eb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1eb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db1eb-134">See also</span></span>

- [<span data-ttu-id="db1eb-135">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db1eb-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="db1eb-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="db1eb-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
