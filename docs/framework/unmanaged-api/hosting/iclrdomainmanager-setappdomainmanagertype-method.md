---
title: ICLRDomainManager::SetAppDomainManagerType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37c94da8295a0ebb96d45e3a8f122d96bc2126c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="e9527-102">ICLRDomainManager::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="e9527-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="e9527-103">Gibt den Typ abgeleitet wurde. die <xref:System.AppDomainManager?displayProperty=nameWithType> Klasse, der den Anwendungsdomänen-Manager, der verwendet wird, um die Standardanwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e9527-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9527-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9527-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9527-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9527-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="e9527-106">[in] Der Anzeigename der Assembly, die den Anwendungstyp der Domänen-Manager enthält; zum Beispiel: "AdMgrExample, Version = 1.0.0.0, Culture = Neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="e9527-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="e9527-107">[in] Der Typname des Anwendungsdomänen-Managers, einschließlich des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="e9527-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="e9527-108">[in] Eine Kombination von [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) Enumerationswerte, die Informationen zu den Anwendungsdomänen-Manager bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e9527-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9527-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e9527-109">Return Value</span></span>  
 <span data-ttu-id="e9527-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9527-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e9527-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9527-111">HRESULT</span></span>|<span data-ttu-id="e9527-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9527-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9527-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9527-113">S_OK</span></span>|<span data-ttu-id="e9527-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e9527-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e9527-115">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e9527-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9527-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9527-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9527-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9527-117">Remarks</span></span>  
 <span data-ttu-id="e9527-118">Derzeit die einzige definierte Wert für `dwInitializeDomainFlags` ist `eInitializeNewDomainFlags_NoSecurityChanges`, weist der common Language Runtime (CLR), dass die Anwendungsdomänen-Managers nicht während der Ausführung ändern von Sicherheitseinstellungen wird der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="e9527-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e9527-119">Dies ermöglicht es der CLR, das Laden von Assemblys zu optimieren, die über die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA).</span><span class="sxs-lookup"><span data-stu-id="e9527-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="e9527-120">Dies kann zu einer erheblichen Verbesserung Startzeit führen, wenn der transitive Abschluss dieser Gruppe von Assemblys groß ist.</span><span class="sxs-lookup"><span data-stu-id="e9527-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9527-121">Wenn der Host gibt `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungsdomänen-Manager, ein <xref:System.InvalidOperationException> wird ausgelöst, wenn versucht wird, die Sicherheit der Anwendungsdomäne ändern.</span><span class="sxs-lookup"><span data-stu-id="e9527-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="e9527-122">Aufrufen der [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)Methode entspricht dem Aufruf `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="e9527-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9527-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9527-123">Requirements</span></span>  
 <span data-ttu-id="e9527-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9527-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9527-125">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e9527-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e9527-126">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9527-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9527-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9527-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9527-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9527-128">See Also</span></span>  
 [<span data-ttu-id="e9527-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="e9527-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="e9527-130">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9527-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [<span data-ttu-id="e9527-131">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e9527-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
