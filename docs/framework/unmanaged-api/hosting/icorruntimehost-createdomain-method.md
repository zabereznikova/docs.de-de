---
title: ICorRuntimeHost::CreateDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 74f17c77e74edb1226dda2d9ebaa9486e1769ce4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762356"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="fa288-102">ICorRuntimeHost::CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="fa288-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="fa288-103">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="fa288-103">Creates an application domain.</span></span> <span data-ttu-id="fa288-104">Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz vom Typ <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fa288-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa288-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa288-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa288-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa288-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="fa288-107">in Ein optionaler Parameter, der verwendet wird, um der Domäne einen anzeigen Amen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="fa288-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="fa288-108">Dieser Anzeige Name kann in Benutzeroberflächen wie z. b. Debuggern angezeigt werden, um die Domäne zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fa288-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="fa288-109">in Ein optionales Array von Zeigern auf- `IIdentity` Instanzen, die durch Sicherheitsrichtlinien zugeordnete Beweise darstellen, um einen Berechtigungs Satz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fa288-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="fa288-110">Ein- `IIdentity` Objekt kann durch Aufrufen der [CreateEvidence](icorruntimehost-createevidence-method.md) -Methode abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fa288-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fa288-111">vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um die Domäne weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fa288-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa288-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa288-112">Return Value</span></span>  
  
|<span data-ttu-id="fa288-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa288-113">HRESULT</span></span>|<span data-ttu-id="fa288-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa288-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa288-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa288-115">S_OK</span></span>|<span data-ttu-id="fa288-116">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fa288-116">The operation was successful.</span></span>|  
|<span data-ttu-id="fa288-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fa288-117">S_FALSE</span></span>|<span data-ttu-id="fa288-118">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa288-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fa288-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa288-119">E_FAIL</span></span>|<span data-ttu-id="fa288-120">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fa288-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fa288-121">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="fa288-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fa288-122">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fa288-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fa288-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa288-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa288-124">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fa288-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa288-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fa288-125">Requirements</span></span>  
 <span data-ttu-id="fa288-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa288-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa288-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fa288-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa288-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fa288-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa288-129">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="fa288-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa288-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa288-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="fa288-131">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa288-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
