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
ms.openlocfilehash: 7c6b328793e6437682ad8d642e611be30e7b0fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702146"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="5d8cd-102">ICLRDomainManager::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="5d8cd-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="5d8cd-103">Gibt den von der-Klasse abgeleiteten Typ <xref:System.AppDomainManager?displayProperty=nameWithType> des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d8cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d8cd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d8cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d8cd-105">Parameters</span></span>  

 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="5d8cd-106">in Der Anzeige Name der Assembly, die den Typ des Anwendungs Domänen-Managers enthält. Beispiel: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf 150s00b3".</span><span class="sxs-lookup"><span data-stu-id="5d8cd-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="5d8cd-107">in Der Typname des Anwendungs Domänen-Managers, einschließlich des Namespace.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="5d8cd-108">in Eine Kombination aus [einitializenewdomainflags](einitializenewdomainflags-enumeration.md) -Enumerationswerten, die Informationen über den Anwendungs Domänen-Manager bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-108">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d8cd-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d8cd-109">Return Value</span></span>  

 <span data-ttu-id="5d8cd-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5d8cd-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d8cd-111">HRESULT</span></span>|<span data-ttu-id="5d8cd-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5d8cd-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d8cd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d8cd-113">S_OK</span></span>|<span data-ttu-id="5d8cd-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="5d8cd-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d8cd-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d8cd-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d8cd-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d8cd-117">Remarks</span></span>  

 <span data-ttu-id="5d8cd-118">Derzeit ist der einzige definierte Wert für `dwInitializeDomainFlags` `eInitializeNewDomainFlags_NoSecurityChanges` , der die Common Language Runtime (CLR) anweist, dass der Anwendungs Domänen-Manager während der Ausführung der Methode keine Sicherheitseinstellungen ändert <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5d8cd-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5d8cd-119">Dadurch kann die CLR das Laden von Assemblys optimieren, die über das Conditional- <xref:System.Security.AllowPartiallyTrustedCallersAttribute> Attribut (APTCA) verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="5d8cd-120">Dies kann zu einer erheblichen Verbesserung der Startzeit führen, wenn die transitiv Schließung dieses Assemblysatzes sehr groß ist.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5d8cd-121">Wenn der Host `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungs Domänen-Manager angibt, wird eine ausgelöst, <xref:System.InvalidOperationException> Wenn versucht wird, die Sicherheit der Anwendungsdomäne zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5d8cd-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="5d8cd-122">Das Aufrufen der [ICLRControl:: abtappdomainmanagertype](iclrcontrol-setappdomainmanagertype-method.md)-Methode entspricht dem Aufrufen `ICLRDomainManager::SetAppDomainManagerType` von mit `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="5d8cd-122">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d8cd-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d8cd-123">Requirements</span></span>  

 <span data-ttu-id="5d8cd-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d8cd-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d8cd-125">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5d8cd-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5d8cd-126">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5d8cd-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d8cd-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d8cd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d8cd-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d8cd-128">See also</span></span>

- [<span data-ttu-id="5d8cd-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="5d8cd-129">Hosting</span></span>](index.md)
- [<span data-ttu-id="5d8cd-130">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d8cd-130">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="5d8cd-131">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5d8cd-131">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
