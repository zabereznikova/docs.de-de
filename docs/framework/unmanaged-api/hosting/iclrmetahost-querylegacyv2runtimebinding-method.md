---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode
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
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 889d8ca00726c0b271a1d43519803af73018b2a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="0fc9e-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode</span><span class="sxs-lookup"><span data-stu-id="0fc9e-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="0fc9e-103">Gibt eine Schnittstelle, die eine Laufzeit darstellt, an die ältere Aktivierungsrichtlinie gebunden wurde, z. B. mit, der `useLegacyV2RuntimeActivationPolicy` -Attribut auf die [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) Konfigurationsdateieintrag, durch direkte Verwendung der Legacyaktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fc9e-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fc9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fc9e-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="0fc9e-106">[in] Der einzige gültige Wert für diesen Parameter ist Required.Currently `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="0fc9e-107">[out] erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-107">[out] Required.</span></span> <span data-ttu-id="0fc9e-108">Wenn diese Methode zurückgibt, enthält einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die eine Laufzeit darstellt, die an eine ältere Aktivierungsrichtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fc9e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0fc9e-109">Return Value</span></span>  
 <span data-ttu-id="0fc9e-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0fc9e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fc9e-111">HRESULT</span></span>|<span data-ttu-id="0fc9e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0fc9e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0fc9e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0fc9e-113">S_OK</span></span>|<span data-ttu-id="0fc9e-114">Die Methode wurde erfolgreich abgeschlossen und hat eine Laufzeit zurückgegeben, die an eine ältere Aktivierungsrichtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="0fc9e-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0fc9e-115">S_FALSE</span></span>|<span data-ttu-id="0fc9e-116">Die Methode wurde erfolgreich abgeschlossen, aber eine ältere Laufzeit wurde noch nicht gebunden.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="0fc9e-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="0fc9e-117">E_NOINTERFACE</span></span>|<span data-ttu-id="0fc9e-118">Die Methode hat eine Laufzeitumgebung gefunden, die an eine ältere Aktivierungsrichtlinie gebunden war, aber `riid` wird von dieser Laufzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fc9e-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fc9e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fc9e-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc9e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fc9e-120">Requirements</span></span>  
 <span data-ttu-id="0fc9e-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc9e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc9e-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0fc9e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0fc9e-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0fc9e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fc9e-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc9e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc9e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fc9e-125">See Also</span></span>  
 [<span data-ttu-id="0fc9e-126">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fc9e-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="0fc9e-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="0fc9e-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
