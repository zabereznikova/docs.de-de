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
ms.openlocfilehash: d6d9e06b6ed40bb0e5a65fd64f8bca7abe3afa84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715679"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="eb971-102">ICorRuntimeHost::CreateDomainEx-Methode</span><span class="sxs-lookup"><span data-stu-id="eb971-102">ICorRuntimeHost::CreateDomainEx Method</span></span>

<span data-ttu-id="eb971-103">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="eb971-103">Creates an application domain.</span></span> <span data-ttu-id="eb971-104">Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz vom Typ <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="eb971-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eb971-105">Diese Methode ermöglicht es dem Aufrufer, eine IAppDomainSetup-Instanz zu übergeben, um zusätzliche Funktionen der zurückgegebenen Instanz zu konfigurieren <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="eb971-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb971-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb971-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb971-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb971-107">Parameters</span></span>  

 `pwzFriendlyName`  
 <span data-ttu-id="eb971-108">in Ein optionaler Parameter, der verwendet wird, um der Domäne einen anzeigen Amen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="eb971-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="eb971-109">Dieser Anzeige Name kann in Benutzeroberflächen wie z. b. Debuggern angezeigt werden, um die Domäne zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="eb971-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="eb971-110">in Ein optionaler Schnittstellen Zeiger vom Typ `IAppDomainSetup` , der durch einen Aufrufen der [ICorRuntimeHost:: | atedomainsetup](icorruntimehost-createdomainsetup-method.md) -Methode abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="eb971-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="eb971-111">in Ein optionales Array von Zeigern auf- `IIdentity` Instanzen, die durch Sicherheitsrichtlinien zugeordnete Beweise darstellen, um einen Berechtigungs Satz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="eb971-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="eb971-112">Ein- `IIdentity` Objekt kann durch Aufrufen der [CreateEvidence](icorruntimehost-createevidence-method.md) -Methode abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eb971-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="eb971-113">vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um die Domäne weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="eb971-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb971-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eb971-114">Return Value</span></span>  
  
|<span data-ttu-id="eb971-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb971-115">HRESULT</span></span>|<span data-ttu-id="eb971-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb971-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb971-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb971-117">S_OK</span></span>|<span data-ttu-id="eb971-118">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="eb971-118">The operation was successful.</span></span>|  
|<span data-ttu-id="eb971-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eb971-119">S_FALSE</span></span>|<span data-ttu-id="eb971-120">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eb971-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="eb971-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb971-121">E_FAIL</span></span>|<span data-ttu-id="eb971-122">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eb971-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="eb971-123">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="eb971-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="eb971-124">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="eb971-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eb971-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb971-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb971-126">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="eb971-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb971-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb971-127">Remarks</span></span>  

 <span data-ttu-id="eb971-128">`CreateDomainEx` erweitert die Funktionen von " [kreatedomain](icorruntimehost-createdomain-method.md) ", indem es dem Aufrufer ermöglicht, eine `IAppDomainSetup` Instanz mit Eigenschafts Werten zum Konfigurieren der Anwendungsdomäne zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="eb971-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb971-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eb971-129">Requirements</span></span>  

 <span data-ttu-id="eb971-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb971-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb971-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="eb971-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb971-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eb971-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb971-133">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="eb971-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb971-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb971-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="eb971-135">CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="eb971-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="eb971-136">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb971-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
