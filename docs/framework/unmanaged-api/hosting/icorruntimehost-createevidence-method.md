---
title: ICorRuntimeHost::CreateEvidence-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca54f779d257314b843838d90ca9996f1eb3237b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081814"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="e62c5-102">ICorRuntimeHost::CreateEvidence-Methode</span><span class="sxs-lookup"><span data-stu-id="e62c5-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="e62c5-103">Ruft einen Schnittstellenzeiger vom Typ <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, wodurch den Host erstellen Sicherheitsbeweis Übergabe an die [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) oder [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e62c5-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e62c5-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e62c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e62c5-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="e62c5-106">[out] Einen Schnittstellenzeiger auf ein <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> Instanz verwendet, um die Sicherheitsbeweis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="e62c5-107">Dieser Zeiger wird als `IUnknown`, sodass Aufrufer, in der Regel aufrufen müssen `QueryInterface` für diese Schnittstelle zum Abrufen der eines Zeigers auf ein <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e62c5-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e62c5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e62c5-108">Return Value</span></span>  
  
|<span data-ttu-id="e62c5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e62c5-109">HRESULT</span></span>|<span data-ttu-id="e62c5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e62c5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e62c5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e62c5-111">S_OK</span></span>|<span data-ttu-id="e62c5-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e62c5-112">The operation was successful.</span></span>|  
|<span data-ttu-id="e62c5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e62c5-113">S_FALSE</span></span>|<span data-ttu-id="e62c5-114">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e62c5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e62c5-115">E_FAIL</span></span>|<span data-ttu-id="e62c5-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e62c5-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e62c5-117">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e62c5-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e62c5-118">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e62c5-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e62c5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e62c5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e62c5-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e62c5-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e62c5-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e62c5-121">Remarks</span></span>  
 <span data-ttu-id="e62c5-122">Diese Methode gibt eine leere Auflistung, die nicht aufgefüllt werden kann, von nativem Code.</span><span class="sxs-lookup"><span data-stu-id="e62c5-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="e62c5-123">Verwenden Sie die <xref:System.Security.Policy.Evidence> Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="e62c5-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e62c5-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e62c5-124">Requirements</span></span>  
 <span data-ttu-id="e62c5-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e62c5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62c5-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e62c5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e62c5-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e62c5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e62c5-128">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e62c5-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62c5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e62c5-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="e62c5-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e62c5-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
