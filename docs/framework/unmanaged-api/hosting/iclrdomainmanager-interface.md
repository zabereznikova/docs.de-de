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
ms.openlocfilehash: c3b8dd67cb7dff4bec5bab192a08461ef13fcbd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436357"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="fdcbb-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdcbb-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="fdcbb-103">Ermöglicht es dem Host den Anwendungsdomänen-Manager an, der die Standardanwendungsdomäne initialisiert werden, sowie an Initialisierungseigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdcbb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fdcbb-104">Methods</span></span>  
  
|<span data-ttu-id="fdcbb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fdcbb-105">Method</span></span>|<span data-ttu-id="fdcbb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdcbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdcbb-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="fdcbb-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="fdcbb-108">Gibt den Typ abgeleitet wurde. die <xref:System.AppDomainManager?displayProperty=nameWithType> Klasse, der den Anwendungsdomänen-Manager, der verwendet wird, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="fdcbb-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="fdcbb-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="fdcbb-110">Legt die Eigenschaften, die verwendet werden, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdcbb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdcbb-111">Remarks</span></span>  
 <span data-ttu-id="fdcbb-112">Um eine Instanz dieser Schnittstelle abzurufen, rufen die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode mit dem Managertyp IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="fdcbb-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdcbb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdcbb-113">Requirements</span></span>  
 <span data-ttu-id="fdcbb-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdcbb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdcbb-115">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fdcbb-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fdcbb-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fdcbb-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdcbb-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdcbb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdcbb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdcbb-118">See Also</span></span>  
 [<span data-ttu-id="fdcbb-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fdcbb-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="fdcbb-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="fdcbb-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
