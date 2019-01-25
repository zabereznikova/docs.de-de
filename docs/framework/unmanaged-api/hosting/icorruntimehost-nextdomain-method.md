---
title: ICorRuntimeHost::NextDomain-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f8e9c91ddddd0e0b14c79bef86c7665ff4e3dcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723320"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="b282e-102">ICorRuntimeHost::NextDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="b282e-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="b282e-103">Ruft einen Schnittstellenzeiger auf die nächste Domäne in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b282e-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b282e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b282e-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b282e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b282e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b282e-106">[in] Der Enumerator, der durch einen Aufruf von erhaltene [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="b282e-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="b282e-107">[out] Einen Schnittstellenzeiger auf das <xref:System._AppDomain?displayProperty=nameWithType> Typ, der die nächste Domäne in der Enumeration oder Null darstellt, wenn keine weitere Domänen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b282e-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b282e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b282e-108">Return Value</span></span>  
  
|<span data-ttu-id="b282e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b282e-109">HRESULT</span></span>|<span data-ttu-id="b282e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b282e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b282e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b282e-111">S_OK</span></span>|<span data-ttu-id="b282e-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b282e-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b282e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b282e-113">S_FALSE</span></span>|<span data-ttu-id="b282e-114">Der Vorgang konnte nicht abgeschlossen, oder es gibt keine weiteren Domänen in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b282e-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="b282e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b282e-115">E_FAIL</span></span>|<span data-ttu-id="b282e-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b282e-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b282e-117">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b282e-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b282e-118">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b282e-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b282e-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b282e-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b282e-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b282e-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b282e-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b282e-121">Requirements</span></span>  
 <span data-ttu-id="b282e-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b282e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b282e-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b282e-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b282e-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b282e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b282e-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b282e-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b282e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b282e-126">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b282e-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b282e-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
