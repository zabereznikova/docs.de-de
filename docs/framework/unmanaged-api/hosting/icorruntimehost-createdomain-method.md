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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea63627bc1e689c93634c8fe8b9048b271758573
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937046"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="daf83-102">ICorRuntimeHost::CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="daf83-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="daf83-103">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="daf83-103">Creates an application domain.</span></span> <span data-ttu-id="daf83-104">Der Aufrufer empfängt einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> in eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="daf83-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf83-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="daf83-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf83-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="daf83-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="daf83-107">[in] Ein optionaler Parameter verwendet, geben einen benutzerfreundlichen Namen der Domäne.</span><span class="sxs-lookup"><span data-stu-id="daf83-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="daf83-108">Dieser Anzeigename kann in Benutzeroberflächen wie der Debugger zur Kennzeichnung der Domäne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="daf83-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="daf83-109">[in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die durch Sicherheitsrichtlinien eines Berechtigungssatzes zugeordneten Beweis darstellen.</span><span class="sxs-lookup"><span data-stu-id="daf83-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="daf83-110">Ein `IIdentity` -Objekt abgerufen werden kann, durch den Aufruf der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="daf83-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="daf83-111">[out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um die Domäne noch weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="daf83-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daf83-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="daf83-112">Return Value</span></span>  
  
|<span data-ttu-id="daf83-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="daf83-113">HRESULT</span></span>|<span data-ttu-id="daf83-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daf83-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="daf83-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="daf83-115">S_OK</span></span>|<span data-ttu-id="daf83-116">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="daf83-116">The operation was successful.</span></span>|  
|<span data-ttu-id="daf83-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="daf83-117">S_FALSE</span></span>|<span data-ttu-id="daf83-118">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="daf83-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="daf83-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="daf83-119">E_FAIL</span></span>|<span data-ttu-id="daf83-120">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="daf83-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="daf83-121">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="daf83-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="daf83-122">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="daf83-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="daf83-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="daf83-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="daf83-124">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="daf83-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="daf83-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daf83-125">Requirements</span></span>  
 <span data-ttu-id="daf83-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf83-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf83-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="daf83-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="daf83-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="daf83-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daf83-129">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="daf83-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf83-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf83-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="daf83-131">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daf83-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
