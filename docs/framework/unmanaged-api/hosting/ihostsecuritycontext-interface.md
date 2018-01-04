---
title: IHostSecurityContext-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ee464e47ad6e333b507c199e1857309f640a37b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="961d2-102">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961d2-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="961d2-103">Ermöglicht die common Language Runtime (CLR) die vom Host implementiert wurde Sicherheitskontextinformationen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="961d2-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="961d2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="961d2-104">Methods</span></span>  
  
|<span data-ttu-id="961d2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="961d2-105">Method</span></span>|<span data-ttu-id="961d2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="961d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="961d2-107">Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="961d2-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="961d2-108">Ruft einen Klon der `IHostSecurityContext` Instanz zurückgegeben, Aufrufen von [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="961d2-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="961d2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="961d2-109">Remarks</span></span>  
 <span data-ttu-id="961d2-110">Ein Host kann alle Codezugriff auf Threadtoken von der CLR und die Benutzer Code steuern.</span><span class="sxs-lookup"><span data-stu-id="961d2-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="961d2-111">Sie können auch sicherstellen, dass vollständige Kontextinformationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="961d2-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="961d2-112">`IHostSecurityContext`kapselt diese Sicherheitskontextinformationen, die für die Common Language Runtime nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="961d2-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="961d2-113">Die Laufzeit erfasst diese Informationen mithilfe `Capture`, und verschiebt sie über Threadpool Worker Item Dispatch, Finalizerausführung und Modul- und Klassenkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="961d2-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="961d2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="961d2-114">Requirements</span></span>  
 <span data-ttu-id="961d2-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="961d2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961d2-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="961d2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="961d2-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="961d2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="961d2-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961d2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961d2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="961d2-119">See Also</span></span>  
 [<span data-ttu-id="961d2-120">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961d2-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="961d2-121">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961d2-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="961d2-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="961d2-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
