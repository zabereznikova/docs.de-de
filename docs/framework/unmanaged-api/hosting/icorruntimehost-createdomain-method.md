---
title: ICorRuntimeHost::CreateDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0da99f05b09d44338a5f4d695fb2a4114f0e1f30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="29714-102">ICorRuntimeHost::CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="29714-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="29714-103">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="29714-103">Creates an application domain.</span></span> <span data-ttu-id="29714-104">Der Aufrufer empfängt einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="29714-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29714-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="29714-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29714-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="29714-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="29714-107">[in] Ein optionaler Parameter verwendet, um der Domäne einen Anzeigenamen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="29714-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="29714-108">Dieser aussagekräftige Name kann in Benutzeroberflächen wie Debuggern zur Kennzeichnung der Domäne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="29714-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="29714-109">[in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die Beweise Sicherheitsrichtlinie darstellen herstellen einen Berechtigungssatz zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="29714-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="29714-110">Ein `IIdentity` -Objekt abgerufen werden kann, durch Aufrufen der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="29714-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="29714-111">[out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um der Domäne weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="29714-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29714-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29714-112">Return Value</span></span>  
  
|<span data-ttu-id="29714-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29714-113">HRESULT</span></span>|<span data-ttu-id="29714-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29714-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29714-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="29714-115">S_OK</span></span>|<span data-ttu-id="29714-116">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="29714-116">The operation was successful.</span></span>|  
|<span data-ttu-id="29714-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="29714-117">S_FALSE</span></span>|<span data-ttu-id="29714-118">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="29714-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="29714-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29714-119">E_FAIL</span></span>|<span data-ttu-id="29714-120">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="29714-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="29714-121">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="29714-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="29714-122">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="29714-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="29714-123">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="29714-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29714-124">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="29714-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29714-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29714-125">Requirements</span></span>  
 <span data-ttu-id="29714-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29714-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29714-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29714-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29714-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="29714-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29714-129">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="29714-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29714-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29714-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="29714-131">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29714-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
