---
title: ICLRDomainManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103921"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="d9f7a-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9f7a-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="d9f7a-103">Ermöglicht dem Host an den Anwendungsdomänen-Manager, der zum Initialisieren von der Standardanwendungsdomäne, und klicken Sie zum Angeben von Eigenschaften zur datenquelleninitialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9f7a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d9f7a-104">Methods</span></span>  
  
|<span data-ttu-id="d9f7a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d9f7a-105">Method</span></span>|<span data-ttu-id="d9f7a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9f7a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9f7a-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="d9f7a-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="d9f7a-108">Gibt an, die von abgeleiteten Typ, der <xref:System.AppDomainManager?displayProperty=nameWithType> -Klasse von den Anwendungsdomänen-Manager, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="d9f7a-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="d9f7a-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="d9f7a-110">Legt die Eigenschaften, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9f7a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9f7a-111">Remarks</span></span>  
 <span data-ttu-id="d9f7a-112">Um eine Instanz dieser Schnittstelle abzurufen, rufen die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode mit den Typ des Managers IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f7a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9f7a-113">Requirements</span></span>  
 <span data-ttu-id="d9f7a-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f7a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f7a-115">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d9f7a-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d9f7a-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d9f7a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9f7a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f7a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f7a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9f7a-118">See also</span></span>

- [<span data-ttu-id="d9f7a-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9f7a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d9f7a-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="d9f7a-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
