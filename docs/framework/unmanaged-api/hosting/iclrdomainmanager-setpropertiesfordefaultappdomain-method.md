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
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702133"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="c156f-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="c156f-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="c156f-103">Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c156f-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c156f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c156f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c156f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c156f-105">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="c156f-106">in Die Anzahl der Einträge in `pwszPropertyNames` und `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="c156f-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="c156f-107">in Ein Array von Eigenschaften Namen oder NULL, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c156f-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="c156f-108">Derzeit ist der einzige Eigenschaftsname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="c156f-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="c156f-109">in Ein Array von Eigenschafts Werten oder NULL, wenn keine Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c156f-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c156f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c156f-110">Return Value</span></span>  

 <span data-ttu-id="c156f-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c156f-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c156f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c156f-112">HRESULT</span></span>|<span data-ttu-id="c156f-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c156f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c156f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c156f-114">S_OK</span></span>|<span data-ttu-id="c156f-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c156f-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="c156f-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="c156f-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="c156f-117">`pwszPropertyNames` enthält einen Eigenschaftsnamen, der von dieser Methode nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c156f-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c156f-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c156f-118">Remarks</span></span>  

 <span data-ttu-id="c156f-119">Der Eigenschafts Wert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste von Assemblys, die über das Conditional- <xref:System.Security.AllowPartiallyTrustedCallersAttribute> Attribut (APTCA) mit dem- <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> Flag verfügen, das für teilweise vertrauenswürdige Aufrufer in der Standard Anwendungsdomäne sichtbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c156f-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c156f-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c156f-120">Requirements</span></span>  

 <span data-ttu-id="c156f-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c156f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c156f-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="c156f-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c156f-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c156f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c156f-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c156f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c156f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c156f-125">See also</span></span>

- [<span data-ttu-id="c156f-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="c156f-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="c156f-127">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c156f-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
