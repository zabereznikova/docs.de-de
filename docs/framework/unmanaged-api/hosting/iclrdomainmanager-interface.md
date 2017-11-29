---
title: ICLRDomainManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75a7e93d26a5c77484d78ad4632bedf8def6a44b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="81ece-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81ece-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="81ece-103">Ermöglicht es dem Host den Anwendungsdomänen-Manager an, der die Standardanwendungsdomäne initialisiert werden, sowie an Initialisierungseigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81ece-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81ece-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="81ece-104">Methods</span></span>  
  
|<span data-ttu-id="81ece-105">Methode</span><span class="sxs-lookup"><span data-stu-id="81ece-105">Method</span></span>|<span data-ttu-id="81ece-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81ece-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81ece-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="81ece-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="81ece-108">Gibt den Typ abgeleitet wurde. die <xref:System.AppDomainManager?displayProperty=nameWithType> Klasse, der den Anwendungsdomänen-Manager, der verwendet wird, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="81ece-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="81ece-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="81ece-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="81ece-110">Legt die Eigenschaften, die verwendet werden, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="81ece-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81ece-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81ece-111">Remarks</span></span>  
 <span data-ttu-id="81ece-112">Um eine Instanz dieser Schnittstelle abzurufen, rufen die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode mit dem Managertyp IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="81ece-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ece-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81ece-113">Requirements</span></span>  
 <span data-ttu-id="81ece-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81ece-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ece-115">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="81ece-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="81ece-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="81ece-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81ece-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ece-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ece-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81ece-118">See Also</span></span>  
 [<span data-ttu-id="81ece-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="81ece-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="81ece-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="81ece-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
