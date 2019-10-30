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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129339"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="70f41-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70f41-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="70f41-103">Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="70f41-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70f41-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="70f41-104">Methods</span></span>  
  
|<span data-ttu-id="70f41-105">Methode</span><span class="sxs-lookup"><span data-stu-id="70f41-105">Method</span></span>|<span data-ttu-id="70f41-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70f41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70f41-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="70f41-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="70f41-108">Gibt den von der <xref:System.AppDomainManager?displayProperty=nameWithType>-Klasse abgeleiteten Typ des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70f41-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="70f41-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="70f41-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="70f41-110">Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="70f41-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70f41-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70f41-111">Remarks</span></span>  
 <span data-ttu-id="70f41-112">Um eine Instanz dieser Schnittstelle abzurufen, müssen Sie die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode mit dem Manager-Typ IID `IID_ICLRDomainManager`aufrufen.</span><span class="sxs-lookup"><span data-stu-id="70f41-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f41-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70f41-113">Requirements</span></span>  
 <span data-ttu-id="70f41-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70f41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f41-115">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="70f41-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="70f41-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="70f41-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70f41-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f41-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70f41-118">See also</span></span>

- [<span data-ttu-id="70f41-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="70f41-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="70f41-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="70f41-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
