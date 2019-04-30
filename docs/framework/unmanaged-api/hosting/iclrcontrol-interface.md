---
title: ICLRControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f70e7958cc9ac198738ed72732fe7b6563c89067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970065"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="46c3e-102">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-102">ICLRControl Interface</span></span>
<span data-ttu-id="46c3e-103">Stellt Methoden, mit denen einen Host aus, um Verweise auf abzurufen, und konfigurieren Sie Aspekte, die common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="46c3e-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46c3e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="46c3e-104">Methods</span></span>  
  
|<span data-ttu-id="46c3e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="46c3e-105">Method</span></span>|<span data-ttu-id="46c3e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46c3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46c3e-107">GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="46c3e-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="46c3e-108">Ruft einen Schnittstellenzeiger auf eine Instanz eines der Managertypen, mit denen der Host zum Konfigurieren der CLR ab.</span><span class="sxs-lookup"><span data-stu-id="46c3e-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="46c3e-109">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="46c3e-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="46c3e-110">Legt die von abgeleiteten Typs <xref:System.AppDomainManager> als Typ für Anwendungsdomänen-Manager.</span><span class="sxs-lookup"><span data-stu-id="46c3e-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46c3e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46c3e-111">Requirements</span></span>  
 <span data-ttu-id="46c3e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c3e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c3e-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46c3e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46c3e-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="46c3e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46c3e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c3e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c3e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46c3e-116">See also</span></span>

- [<span data-ttu-id="46c3e-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="46c3e-118">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="46c3e-119">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="46c3e-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="46c3e-121">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="46c3e-122">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="46c3e-123">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="46c3e-124">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46c3e-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="46c3e-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="46c3e-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
