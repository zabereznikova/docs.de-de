---
title: ICorRuntimeHost::EnumDomains-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e4db2330c6d46610bbb3da8b732b1c098659c97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729079"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="a0884-102">ICorRuntimeHost::EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="a0884-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="a0884-103">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="a0884-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0884-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0884-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0884-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0884-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a0884-106">[out] Ein Enumerator für die Domänen.</span><span class="sxs-lookup"><span data-stu-id="a0884-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0884-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0884-107">Return Value</span></span>  
  
|<span data-ttu-id="a0884-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0884-108">HRESULT</span></span>|<span data-ttu-id="a0884-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0884-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0884-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0884-110">S_OK</span></span>|<span data-ttu-id="a0884-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a0884-111">The operation was successful.</span></span>|  
|<span data-ttu-id="a0884-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a0884-112">S_FALSE</span></span>|<span data-ttu-id="a0884-113">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a0884-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a0884-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0884-114">E_FAIL</span></span>|<span data-ttu-id="a0884-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0884-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a0884-116">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0884-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a0884-117">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a0884-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0884-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0884-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0884-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0884-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0884-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0884-120">Requirements</span></span>  
 <span data-ttu-id="a0884-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0884-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0884-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0884-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0884-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a0884-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0884-124">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a0884-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0884-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0884-125">See also</span></span>
- [<span data-ttu-id="a0884-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0884-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
