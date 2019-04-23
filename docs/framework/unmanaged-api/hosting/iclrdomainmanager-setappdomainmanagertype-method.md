---
title: ICLRDomainManager::SetAppDomainManagerType-Methode
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cfef7d929d40996716a02a4db51630827011a68
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183247"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="750e8-102">ICLRDomainManager::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="750e8-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="750e8-103">Gibt an, die von abgeleiteten Typ, der <xref:System.AppDomainManager?displayProperty=nameWithType> -Klasse von den Anwendungsdomänen-Manager, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="750e8-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="750e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="750e8-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="750e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="750e8-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="750e8-106">[in] Der Anzeigename der Assembly, die die Anwendung-Typ enthält; Zum Beispiel: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="750e8-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="750e8-107">[in] Der Typname, der den Anwendungsdomänen-Manager, einschließlich des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="750e8-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="750e8-108">[in] Eine Kombination von [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) Enumerationswerte, der Informationen zu den Anwendungsdomänen-Manager bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="750e8-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="750e8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="750e8-109">Return Value</span></span>  
 <span data-ttu-id="750e8-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="750e8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="750e8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="750e8-111">HRESULT</span></span>|<span data-ttu-id="750e8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="750e8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="750e8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="750e8-113">S_OK</span></span>|<span data-ttu-id="750e8-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="750e8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="750e8-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="750e8-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="750e8-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="750e8-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="750e8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="750e8-117">Remarks</span></span>  
 <span data-ttu-id="750e8-118">Derzeit die einzige definierte Wert für `dwInitializeDomainFlags` ist `eInitializeNewDomainFlags_NoSecurityChanges`, die der common Language Runtime (CLR) teilt mit, dass die Anwendungsdomänen-Manager nicht während der Ausführung ändern von Sicherheitseinstellungen wird der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="750e8-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="750e8-119">Dies ermöglicht der CLR, das Laden von Assemblys zu optimieren, die die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA).</span><span class="sxs-lookup"><span data-stu-id="750e8-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="750e8-120">Dies kann zu einer erheblichen Verbesserung Startzeit führen, wenn der transitive Abschluss von diesem Satz von Assemblys groß ist.</span><span class="sxs-lookup"><span data-stu-id="750e8-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="750e8-121">Wenn der Host gibt `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungsdomänen-Manager, ein <xref:System.InvalidOperationException> wird ausgelöst, wenn es versucht wird, auf die Sicherheit der Anwendungsdomäne zu ändern.</span><span class="sxs-lookup"><span data-stu-id="750e8-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="750e8-122">Aufrufen der [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)Methode entspricht dem Aufruf `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="750e8-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="750e8-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="750e8-123">Requirements</span></span>  
 <span data-ttu-id="750e8-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="750e8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="750e8-125">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="750e8-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="750e8-126">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="750e8-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="750e8-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="750e8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750e8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="750e8-128">See also</span></span>

- [<span data-ttu-id="750e8-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="750e8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="750e8-130">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="750e8-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="750e8-131">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="750e8-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
