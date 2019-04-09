---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c42297e848844617ffdc6c85c81846b5805eb4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181333"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="7c721-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7c721-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="7c721-103">Legt die Eigenschaften, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c721-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c721-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c721-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c721-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c721-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="7c721-106">[in] Die Anzahl der Einträge im `pwszPropertyNames` und `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="7c721-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="7c721-107">[in] Ein Array von Eigenschaftennamen oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7c721-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="7c721-108">Derzeit ist der einzige Eigenschaftenname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="7c721-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="7c721-109">[in] Ein Array von Eigenschaftswerten oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7c721-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c721-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7c721-110">Return Value</span></span>  
 <span data-ttu-id="7c721-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c721-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7c721-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c721-112">HRESULT</span></span>|<span data-ttu-id="7c721-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c721-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c721-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c721-114">S_OK</span></span>|<span data-ttu-id="7c721-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7c721-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="7c721-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="7c721-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|`pwszPropertyNames` <span data-ttu-id="7c721-117">enthält einen Eigenschaftennamen an, der von dieser Methode nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="7c721-117">includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c721-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c721-118">Remarks</span></span>  
 <span data-ttu-id="7c721-119">Der Eigenschaftswert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste der Assemblys, die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), mit der <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> -Flag, das in der standardanwendung für teilweise vertrauenswürdige Aufrufer sichtbar gemacht werden sollen die Domäne.</span><span class="sxs-lookup"><span data-stu-id="7c721-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c721-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c721-120">Requirements</span></span>  
 <span data-ttu-id="7c721-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c721-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c721-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7c721-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7c721-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c721-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c721-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7c721-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c721-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c721-125">See also</span></span>

- [<span data-ttu-id="7c721-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="7c721-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="7c721-127">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c721-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
