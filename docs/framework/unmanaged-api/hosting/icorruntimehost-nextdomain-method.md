---
title: ICorRuntimeHost::NextDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e539cd4071fe9713ed53f66c2f67b24b787d259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="0c916-102">ICorRuntimeHost::NextDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="0c916-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="0c916-103">Ruft einen Schnittstellenzeiger auf die nächste Domäne in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0c916-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c916-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c916-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c916-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c916-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0c916-106">[in] Der Enumerator, der durch einen Aufruf abgerufen wurde [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c916-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0c916-107">[out] Einen Schnittstellenzeiger auf die <xref:System._AppDomain?displayProperty=nameWithType> Typ, der die nächste Domäne in der Enumeration oder Null darstellt, wenn keine weiteren Domänen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0c916-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c916-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0c916-108">Return Value</span></span>  
  
|<span data-ttu-id="0c916-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c916-109">HRESULT</span></span>|<span data-ttu-id="0c916-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c916-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c916-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c916-111">S_OK</span></span>|<span data-ttu-id="0c916-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0c916-112">The operation was successful.</span></span>|  
|<span data-ttu-id="0c916-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0c916-113">S_FALSE</span></span>|<span data-ttu-id="0c916-114">Fehler beim Abschließen des Vorgangs, oder es sind keine weiteren Domänen in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0c916-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="0c916-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c916-115">E_FAIL</span></span>|<span data-ttu-id="0c916-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c916-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0c916-117">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c916-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0c916-118">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0c916-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c916-119">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0c916-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c916-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0c916-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c916-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c916-121">Requirements</span></span>  
 <span data-ttu-id="0c916-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c916-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c916-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c916-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c916-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0c916-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c916-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0c916-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c916-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c916-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="0c916-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c916-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
