---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690287bf54f98c19298504ee3058a59ef88a87f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433160"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="db7db-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode</span><span class="sxs-lookup"><span data-stu-id="db7db-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="db7db-103">Bindet die aktuelle Laufzeit für alle älteren common Language Runtime (CLR) Version 2 Aktivierung richtlinienentscheidungen.</span><span class="sxs-lookup"><span data-stu-id="db7db-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db7db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db7db-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="db7db-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db7db-105">Return Value</span></span>  
 <span data-ttu-id="db7db-106">Diese Methode gibt die folgenden spezifischen HRESULTs zurück:</span><span class="sxs-lookup"><span data-stu-id="db7db-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="db7db-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db7db-107">HRESULT</span></span>|<span data-ttu-id="db7db-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db7db-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db7db-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="db7db-109">S_OK</span></span>|<span data-ttu-id="db7db-110">Bindung erfolgreich war oder diese Laufzeit wurde bereits als CLR-Version 2 Aktivierung Richtlinie legacylaufzeit gebunden.</span><span class="sxs-lookup"><span data-stu-id="db7db-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="db7db-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="db7db-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="db7db-112">Eine andere Runtime wurde bereits an die ältere 2 Aktivierungsrichtlinie einer CLR-Version gebunden.</span><span class="sxs-lookup"><span data-stu-id="db7db-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db7db-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db7db-113">Remarks</span></span>  
 <span data-ttu-id="db7db-114">Wenn die aktuelle Laufzeit bereits für alle legacy CLR Version 2 Aktivierung richtlinienentscheidungen gebunden ist (z. B. mithilfe der `useLegacyV2RuntimeActivationPolicy` -Attribut der [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), diese Methode Ein Fehlerergebnis wird nicht zurückgegeben werden. Stattdessen ist das Ergebnis S_OK zurück, so wie es der Fall wäre, wenn die Methode erfolgreich ältere Aktivierungsrichtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="db7db-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db7db-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db7db-115">Requirements</span></span>  
 <span data-ttu-id="db7db-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db7db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db7db-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="db7db-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="db7db-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db7db-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db7db-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db7db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7db-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db7db-120">See Also</span></span>  
 [<span data-ttu-id="db7db-121">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db7db-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="db7db-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="db7db-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="db7db-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="db7db-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="db7db-124">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="db7db-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
