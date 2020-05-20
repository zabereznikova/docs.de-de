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
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615836"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="33b7f-102">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-102">ICLRControl Interface</span></span>
<span data-ttu-id="33b7f-103">Stellt Methoden bereit, mit denen ein Host Verweise auf die Common Language Runtime (CLR) erhalten und Aspekte von diesen konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="33b7f-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33b7f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="33b7f-104">Methods</span></span>  
  
|<span data-ttu-id="33b7f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="33b7f-105">Method</span></span>|<span data-ttu-id="33b7f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33b7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33b7f-107">GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="33b7f-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="33b7f-108">Ruft einen Schnittstellen Zeiger auf eine Instanz eines beliebigen Manager Typs ab, der vom Host zum Konfigurieren der CLR verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="33b7f-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="33b7f-109">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="33b7f-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="33b7f-110">Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungs Domänen-Manager fest.</span><span class="sxs-lookup"><span data-stu-id="33b7f-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33b7f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33b7f-111">Requirements</span></span>  
 <span data-ttu-id="33b7f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33b7f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b7f-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="33b7f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33b7f-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33b7f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33b7f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b7f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b7f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33b7f-116">See also</span></span>

- [<span data-ttu-id="33b7f-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="33b7f-118">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="33b7f-119">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="33b7f-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="33b7f-121">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="33b7f-122">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="33b7f-123">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="33b7f-124">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b7f-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="33b7f-125">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="33b7f-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
