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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984762"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="a16f3-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a16f3-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="a16f3-103">Legt die Eigenschaften, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a16f3-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a16f3-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a16f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a16f3-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="a16f3-106">[in] Die Anzahl der Einträge im `pwszPropertyNames` und `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="a16f3-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="a16f3-107">[in] Ein Array von Eigenschaftennamen oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a16f3-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="a16f3-108">Derzeit ist der einzige Eigenschaftenname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="a16f3-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="a16f3-109">[in] Ein Array von Eigenschaftswerten oder Null, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a16f3-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a16f3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a16f3-110">Return Value</span></span>  
 <span data-ttu-id="a16f3-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a16f3-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a16f3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a16f3-112">HRESULT</span></span>|<span data-ttu-id="a16f3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a16f3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a16f3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a16f3-114">S_OK</span></span>|<span data-ttu-id="a16f3-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a16f3-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a16f3-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="a16f3-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="a16f3-117">`pwszPropertyNames` enthält einen Eigenschaftennamen an, der von dieser Methode nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="a16f3-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a16f3-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a16f3-118">Remarks</span></span>  
 <span data-ttu-id="a16f3-119">Der Eigenschaftswert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste der Assemblys, die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), mit der <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> -Flag, das in der standardanwendung für teilweise vertrauenswürdige Aufrufer sichtbar gemacht werden sollen die Domäne.</span><span class="sxs-lookup"><span data-stu-id="a16f3-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a16f3-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a16f3-120">Requirements</span></span>  
 <span data-ttu-id="a16f3-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a16f3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a16f3-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a16f3-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a16f3-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a16f3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a16f3-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a16f3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16f3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a16f3-125">See also</span></span>

- [<span data-ttu-id="a16f3-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="a16f3-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="a16f3-127">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a16f3-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
