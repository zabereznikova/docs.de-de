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
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120255"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="a1ebf-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode</span><span class="sxs-lookup"><span data-stu-id="a1ebf-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="a1ebf-103">Bindet die aktuelle Laufzeit für alle Entscheidungen zur Aktivierung der Richtlinie für Legacy-Common Language Runtime (CLR), Version 2.</span><span class="sxs-lookup"><span data-stu-id="a1ebf-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ebf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1ebf-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a1ebf-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1ebf-105">Return Value</span></span>  
 <span data-ttu-id="a1ebf-106">Diese Methode gibt die folgenden spezifischen HRESULTs zurück:</span><span class="sxs-lookup"><span data-stu-id="a1ebf-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="a1ebf-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1ebf-107">HRESULT</span></span>|<span data-ttu-id="a1ebf-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1ebf-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1ebf-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1ebf-109">S_OK</span></span>|<span data-ttu-id="a1ebf-110">Die Bindung wurde erfolgreich ausgeführt, oder diese Laufzeit war bereits als Common Language Runtime für die CLR Version 2-Aktivierungs Richtlinie gebunden.</span><span class="sxs-lookup"><span data-stu-id="a1ebf-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="a1ebf-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="a1ebf-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="a1ebf-112">Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.</span><span class="sxs-lookup"><span data-stu-id="a1ebf-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1ebf-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1ebf-113">Remarks</span></span>  
 <span data-ttu-id="a1ebf-114">Wenn die aktuelle Laufzeit bereits für alle Richtlinien zur Aktivierung der Common Language Runtime (CLR, Version 2) gebunden ist (z. b. durch Verwendung des `useLegacyV2RuntimeActivationPolicy`-Attributs für das [\<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), wird von dieser Methode kein Fehler Ergebnis zurückgegeben. Stattdessen ist das Ergebnis S_OK, genauso wie es wäre, wenn die Methode die Legacy Aktivierungs Richtlinie erfolgreich gebunden hätte.</span><span class="sxs-lookup"><span data-stu-id="a1ebf-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ebf-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1ebf-115">Requirements</span></span>  
 <span data-ttu-id="a1ebf-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ebf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ebf-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a1ebf-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a1ebf-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a1ebf-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1ebf-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ebf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ebf-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1ebf-120">See also</span></span>

- [<span data-ttu-id="a1ebf-121">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1ebf-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a1ebf-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1ebf-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a1ebf-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="a1ebf-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="a1ebf-124">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="a1ebf-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
