---
title: ICorRuntimeHost::CreateEvidence-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateEvidence
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c050d8d610b32d2e8421a5d61e36cee151085e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="1b2a2-102">ICorRuntimeHost::CreateEvidence-Methode</span><span class="sxs-lookup"><span data-stu-id="1b2a2-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="1b2a2-103">Ruft einen Schnittstellenzeiger vom Typ <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, dadurch wird den Host erstellen Sicherheitsbeweise Übergabe an die [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) oder [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b2a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b2a2-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b2a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b2a2-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="1b2a2-106">[out] Einen Schnittstellenzeiger zu einem <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> Instanz verwendet, um den Sicherheitsbeweis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="1b2a2-107">This-Zeiger typisiert ist `IUnknown`, sodass Aufrufer in der Regel aufrufen sollte `QueryInterface` für diese Schnittstelle, um einen Zeiger auf eine <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b2a2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b2a2-108">Return Value</span></span>  
  
|<span data-ttu-id="1b2a2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b2a2-109">HRESULT</span></span>|<span data-ttu-id="1b2a2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b2a2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b2a2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b2a2-111">S_OK</span></span>|<span data-ttu-id="1b2a2-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-112">The operation was successful.</span></span>|  
|<span data-ttu-id="1b2a2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1b2a2-113">S_FALSE</span></span>|<span data-ttu-id="1b2a2-114">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="1b2a2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b2a2-115">E_FAIL</span></span>|<span data-ttu-id="1b2a2-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="1b2a2-117">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="1b2a2-118">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b2a2-119">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="1b2a2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b2a2-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b2a2-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b2a2-121">Remarks</span></span>  
 <span data-ttu-id="1b2a2-122">Diese Methode gibt eine leere Auflistung, die aufgefüllt werden, kann nicht von systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="1b2a2-123">Verwenden Sie die <xref:System.Security.Policy.Evidence> Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="1b2a2-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b2a2-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b2a2-124">Requirements</span></span>  
 <span data-ttu-id="1b2a2-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b2a2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b2a2-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b2a2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b2a2-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b2a2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b2a2-128">**.NET Framework-Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1b2a2-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2a2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b2a2-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="1b2a2-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b2a2-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
