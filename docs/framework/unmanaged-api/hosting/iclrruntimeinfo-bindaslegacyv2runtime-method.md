---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="7457d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode</span><span class="sxs-lookup"><span data-stu-id="7457d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="7457d-103">Bindet die aktuelle Laufzeit für alle älteren common Language Runtime (CLR) Version 2 Aktivierung richtlinienentscheidungen.</span><span class="sxs-lookup"><span data-stu-id="7457d-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7457d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7457d-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7457d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7457d-105">Return Value</span></span>  
 <span data-ttu-id="7457d-106">Diese Methode gibt die folgenden spezifischen HRESULTs zurück:</span><span class="sxs-lookup"><span data-stu-id="7457d-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="7457d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7457d-107">HRESULT</span></span>|<span data-ttu-id="7457d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7457d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7457d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7457d-109">S_OK</span></span>|<span data-ttu-id="7457d-110">Bindung erfolgreich war oder diese Laufzeit wurde bereits als CLR-Version 2 Aktivierung Richtlinie legacylaufzeit gebunden.</span><span class="sxs-lookup"><span data-stu-id="7457d-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="7457d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="7457d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="7457d-112">Eine andere Runtime wurde bereits an die ältere 2 Aktivierungsrichtlinie einer CLR-Version gebunden.</span><span class="sxs-lookup"><span data-stu-id="7457d-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7457d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7457d-113">Remarks</span></span>  
 <span data-ttu-id="7457d-114">Wenn die aktuelle Laufzeit bereits für alle legacy CLR Version 2 Aktivierung richtlinienentscheidungen gebunden ist (z. B. mithilfe der `useLegacyV2RuntimeActivationPolicy` -Attribut der [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), diese Methode Ein Fehlerergebnis wird nicht zurückgegeben werden. Stattdessen ist das Ergebnis S_OK zurück, so wie es der Fall wäre, wenn die Methode erfolgreich ältere Aktivierungsrichtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="7457d-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7457d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7457d-115">Requirements</span></span>  
 <span data-ttu-id="7457d-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7457d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7457d-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7457d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7457d-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7457d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7457d-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7457d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7457d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7457d-120">See Also</span></span>  
 [<span data-ttu-id="7457d-121">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7457d-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="7457d-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7457d-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="7457d-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="7457d-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="7457d-124">\<Startup >-Element</span><span class="sxs-lookup"><span data-stu-id="7457d-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
