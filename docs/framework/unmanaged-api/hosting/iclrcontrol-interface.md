---
title: ICLRControl-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl
helpviewer_keywords: ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98b41ea0062534d9e990a7fe366e8f746ae87f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="c041d-102">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-102">ICLRControl Interface</span></span>
<span data-ttu-id="c041d-103">Stellt Methoden, die zum Zulassen von eines Hosts zum Abrufen der Verweise auf und Konfigurieren der Aspekte, die common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="c041d-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c041d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c041d-104">Methods</span></span>  
  
|<span data-ttu-id="c041d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c041d-105">Method</span></span>|<span data-ttu-id="c041d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c041d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c041d-107">GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="c041d-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="c041d-108">Ruft einen Schnittstellenzeiger zu einer Instanz von den Manager-Typen, die der Host so konfigurieren Sie die CLR verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="c041d-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="c041d-109">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="c041d-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="c041d-110">Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungsdomänen-Manager.</span><span class="sxs-lookup"><span data-stu-id="c041d-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c041d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c041d-111">Requirements</span></span>  
 <span data-ttu-id="c041d-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c041d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c041d-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c041d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c041d-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c041d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c041d-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c041d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c041d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c041d-116">See Also</span></span>  
 [<span data-ttu-id="c041d-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="c041d-118">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="c041d-119">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="c041d-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="c041d-121">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="c041d-122">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="c041d-123">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="c041d-124">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c041d-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="c041d-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c041d-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
