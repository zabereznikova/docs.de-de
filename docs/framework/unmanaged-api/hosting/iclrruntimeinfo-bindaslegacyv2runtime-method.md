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
ms.openlocfilehash: f0a03ecce49bbc3c1c03d037c9be31a8e994259d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732091"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="2564d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode</span><span class="sxs-lookup"><span data-stu-id="2564d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="2564d-103">Bindet die aktuelle Laufzeit für alle Entscheidungen zur Aktivierung der Richtlinie für Legacy-Common Language Runtime (CLR), Version 2.</span><span class="sxs-lookup"><span data-stu-id="2564d-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2564d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2564d-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2564d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2564d-105">Return Value</span></span>  

 <span data-ttu-id="2564d-106">Diese Methode gibt die folgenden spezifischen HRESULTs zurück:</span><span class="sxs-lookup"><span data-stu-id="2564d-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="2564d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2564d-107">HRESULT</span></span>|<span data-ttu-id="2564d-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2564d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2564d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2564d-109">S_OK</span></span>|<span data-ttu-id="2564d-110">Die Bindung wurde erfolgreich ausgeführt, oder diese Laufzeit war bereits als Common Language Runtime für die CLR Version 2-Aktivierungs Richtlinie gebunden.</span><span class="sxs-lookup"><span data-stu-id="2564d-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="2564d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="2564d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="2564d-112">Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.</span><span class="sxs-lookup"><span data-stu-id="2564d-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2564d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2564d-113">Remarks</span></span>  

 <span data-ttu-id="2564d-114">Wenn die aktuelle Laufzeit bereits für alle Richtlinien zur Aktivierung der Common Language Runtime (CLR, Version 2) gebunden ist (z. b. durch Verwendung des- `useLegacyV2RuntimeActivationPolicy` Attributs für das- [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), wird von dieser Methode kein Fehler Ergebnis zurückgegeben. stattdessen wird das Ergebnis S_OK, genauso wie es wäre, wenn die Methode die Legacy Aktivierungs Richtlinie erfolgreich gebunden hätte.</span><span class="sxs-lookup"><span data-stu-id="2564d-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2564d-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2564d-115">Requirements</span></span>  

 <span data-ttu-id="2564d-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2564d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2564d-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2564d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2564d-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2564d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2564d-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2564d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2564d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2564d-120">See also</span></span>

- [<span data-ttu-id="2564d-121">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2564d-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2564d-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2564d-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2564d-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="2564d-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="2564d-124">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="2564d-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
