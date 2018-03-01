---
title: ICorRuntimeHost::EnumDomains-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f12135134e38b3f52c66aa951d61a3da7cf5fa50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="85777-102">ICorRuntimeHost::EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="85777-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="85777-103">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="85777-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85777-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85777-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85777-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85777-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="85777-106">[out] Ein Enumerator für die Domänen.</span><span class="sxs-lookup"><span data-stu-id="85777-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85777-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85777-107">Return Value</span></span>  
  
|<span data-ttu-id="85777-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85777-108">HRESULT</span></span>|<span data-ttu-id="85777-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85777-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85777-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85777-110">S_OK</span></span>|<span data-ttu-id="85777-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="85777-111">The operation was successful.</span></span>|  
|<span data-ttu-id="85777-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="85777-112">S_FALSE</span></span>|<span data-ttu-id="85777-113">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="85777-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="85777-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85777-114">E_FAIL</span></span>|<span data-ttu-id="85777-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="85777-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="85777-116">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="85777-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="85777-117">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="85777-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="85777-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="85777-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85777-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="85777-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85777-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85777-120">Requirements</span></span>  
 <span data-ttu-id="85777-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85777-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85777-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85777-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85777-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85777-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85777-124">**.NET Framework-Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="85777-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85777-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85777-125">See Also</span></span>  
 [<span data-ttu-id="85777-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85777-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
