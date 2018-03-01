---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de72568f5908dc89c9a4105c927cfba6c7366b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="e8f5e-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="e8f5e-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="e8f5e-103">Legt die Eigenschaften, die verwendet werden, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8f5e-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8f5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8f5e-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="e8f5e-106">[in] Die Anzahl der Einträge im `pwszPropertyNames` und `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="e8f5e-107">[in] Ein Array von Namen von Eigenschaften oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="e8f5e-108">Derzeit ist der einzige Eigenschaftenname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="e8f5e-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="e8f5e-109">[in] Ein Array von Eigenschaftswerten oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8f5e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8f5e-110">Return Value</span></span>  
 <span data-ttu-id="e8f5e-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e8f5e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8f5e-112">HRESULT</span></span>|<span data-ttu-id="e8f5e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8f5e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8f5e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8f5e-114">S_OK</span></span>|<span data-ttu-id="e8f5e-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="e8f5e-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="e8f5e-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="e8f5e-117">`pwszPropertyNames`enthält einen Eigenschaftsnamen, der von dieser Methode nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8f5e-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8f5e-118">Remarks</span></span>  
 <span data-ttu-id="e8f5e-119">Der Eigenschaftswert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste der Assemblys, die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA) mit dem <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> -Flag, das in der standardanwendung für teilweise vertrauenswürdige Aufrufer sichtbar gemacht werden sollen Domäne.</span><span class="sxs-lookup"><span data-stu-id="e8f5e-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f5e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8f5e-120">Requirements</span></span>  
 <span data-ttu-id="e8f5e-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f5e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f5e-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e8f5e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e8f5e-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8f5e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8f5e-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f5e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f5e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8f5e-125">See Also</span></span>  
 [<span data-ttu-id="e8f5e-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="e8f5e-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="e8f5e-127">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8f5e-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
