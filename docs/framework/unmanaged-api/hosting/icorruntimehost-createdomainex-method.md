---
title: ICorRuntimeHost::CreateDomainEx-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158924"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="50103-102">ICorRuntimeHost::CreateDomainEx-Methode</span><span class="sxs-lookup"><span data-stu-id="50103-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="50103-103">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="50103-103">Creates an application domain.</span></span> <span data-ttu-id="50103-104">Der Aufrufer empfängt einen Schnittstellenzeiger, der Typ <xref:System._AppDomain>, um eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50103-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50103-105">Diese Methode ermöglicht den Aufrufer die Übergabe einer IAppDomainSetup-Instanz zum Konfigurieren der zusätzlichen Features des zurückgegebenen <xref:System._AppDomain> Instanz.</span><span class="sxs-lookup"><span data-stu-id="50103-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50103-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="50103-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50103-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="50103-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="50103-108">[in] Ein optionaler Parameter verwendet, geben einen benutzerfreundlichen Namen der Domäne.</span><span class="sxs-lookup"><span data-stu-id="50103-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="50103-109">Dieser Anzeigename kann in Benutzeroberflächen wie der Debugger zur Kennzeichnung der Domäne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50103-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="50103-110">[in] Ein optionaler Schnittstellenzeiger vom Typ `IAppDomainSetup`, erreicht durch einen Aufruf der [ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="50103-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="50103-111">[in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die durch Sicherheitsrichtlinien eines Berechtigungssatzes zugeordneten Beweis darstellen.</span><span class="sxs-lookup"><span data-stu-id="50103-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="50103-112">Ein `IIdentity` -Objekt abgerufen werden kann, durch den Aufruf der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="50103-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="50103-113">[out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um die Domäne noch weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="50103-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50103-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50103-114">Return Value</span></span>  
  
|<span data-ttu-id="50103-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50103-115">HRESULT</span></span>|<span data-ttu-id="50103-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50103-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50103-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="50103-117">S_OK</span></span>|<span data-ttu-id="50103-118">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="50103-118">The operation was successful.</span></span>|  
|<span data-ttu-id="50103-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="50103-119">S_FALSE</span></span>|<span data-ttu-id="50103-120">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="50103-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="50103-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50103-121">E_FAIL</span></span>|<span data-ttu-id="50103-122">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50103-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="50103-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50103-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="50103-124">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="50103-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50103-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50103-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50103-126">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="50103-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50103-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50103-127">Remarks</span></span>  
 <span data-ttu-id="50103-128">`CreateDomainEx` Erweitert die Möglichkeiten von [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) indem ermöglicht den Aufrufer die Übergabe in einem `IAppDomainSetup` Instanz mit Eigenschaftswerten für das Konfigurieren der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="50103-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50103-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50103-129">Requirements</span></span>  
 <span data-ttu-id="50103-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50103-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50103-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50103-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50103-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50103-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50103-133">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="50103-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50103-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50103-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="50103-135">CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50103-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="50103-136">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50103-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
