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
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129329"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="acc33-102">ICLRDomainManager::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="acc33-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="acc33-103">Gibt den von der <xref:System.AppDomainManager?displayProperty=nameWithType>-Klasse abgeleiteten Typ des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="acc33-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acc33-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acc33-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="acc33-106">in Der Anzeige Name der Assembly, die den Typ des Anwendungs Domänen-Managers enthält. Beispiel: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf 150s00b3".</span><span class="sxs-lookup"><span data-stu-id="acc33-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="acc33-107">in Der Typname des Anwendungs Domänen-Managers, einschließlich des Namespace.</span><span class="sxs-lookup"><span data-stu-id="acc33-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="acc33-108">in Eine Kombination aus [einitializenewdomainflags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) -Enumerationswerten, die Informationen über den Anwendungs Domänen-Manager bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acc33-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acc33-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="acc33-109">Return Value</span></span>  
 <span data-ttu-id="acc33-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="acc33-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="acc33-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acc33-111">HRESULT</span></span>|<span data-ttu-id="acc33-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acc33-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acc33-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="acc33-113">S_OK</span></span>|<span data-ttu-id="acc33-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="acc33-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="acc33-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acc33-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acc33-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="acc33-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acc33-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acc33-117">Remarks</span></span>  
 <span data-ttu-id="acc33-118">Derzeit ist der einzige definierte Wert für `dwInitializeDomainFlags` `eInitializeNewDomainFlags_NoSecurityChanges`, der die Common Language Runtime (CLR) anweist, dass der Anwendungs Domänen-Manager während der Ausführung der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>-Methode die Sicherheitseinstellungen nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="acc33-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="acc33-119">Dadurch kann die CLR das Laden von Assemblys optimieren, die über das APTCA-Attribut (Conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute>) verfügen.</span><span class="sxs-lookup"><span data-stu-id="acc33-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="acc33-120">Dies kann zu einer erheblichen Verbesserung der Startzeit führen, wenn die transitiv Schließung dieses Assemblysatzes sehr groß ist.</span><span class="sxs-lookup"><span data-stu-id="acc33-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="acc33-121">Wenn der Host `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungs Domänen-Manager angibt, wird eine <xref:System.InvalidOperationException> ausgelöst, wenn versucht wird, die Sicherheit der Anwendungsdomäne zu ändern.</span><span class="sxs-lookup"><span data-stu-id="acc33-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="acc33-122">Das Aufrufen der [ICLRControl:: abtappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)-Methode entspricht dem Aufrufen von `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="acc33-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc33-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acc33-123">Requirements</span></span>  
 <span data-ttu-id="acc33-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acc33-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc33-125">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="acc33-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="acc33-126">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="acc33-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acc33-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc33-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc33-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acc33-128">See also</span></span>

- [<span data-ttu-id="acc33-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="acc33-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="acc33-130">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acc33-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="acc33-131">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="acc33-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
