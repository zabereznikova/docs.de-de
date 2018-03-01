---
title: ICLRRuntimeInfo::IsStarted-Methode
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
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 991470ca0df3e0cf0470a8c40d3e8e4c40d96026
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="e43cd-102">ICLRRuntimeInfo::IsStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="e43cd-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="e43cd-103">Gibt an, ob die Laufzeit gestartet wurde (d. h. ob der [ICLRRuntimeHost:: Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) aufgerufen wurde und erfolgreich war).</span><span class="sxs-lookup"><span data-stu-id="e43cd-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e43cd-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e43cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e43cd-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="e43cd-106">[out] `true` Wenn diese Runtime vorhanden, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e43cd-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="e43cd-107">[out] Gibt die Flags, die zum Starten von der Laufzeitmoduls verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e43cd-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e43cd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e43cd-108">Return Value</span></span>  
 <span data-ttu-id="e43cd-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e43cd-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e43cd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e43cd-110">HRESULT</span></span>|<span data-ttu-id="e43cd-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e43cd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e43cd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e43cd-112">S_OK</span></span>|<span data-ttu-id="e43cd-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e43cd-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="e43cd-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e43cd-114">E_NOTIMPL</span></span>|<span data-ttu-id="e43cd-115">Die Version der common Language Runtime (CLR) ist älter als die CLR-Version in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e43cd-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e43cd-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e43cd-116">Remarks</span></span>  
 <span data-ttu-id="e43cd-117">Diese Methode funktioniert nicht mit CLR-Versionen älter als die CLR-Version in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e43cd-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43cd-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e43cd-118">Requirements</span></span>  
 <span data-ttu-id="e43cd-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43cd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43cd-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e43cd-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e43cd-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e43cd-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e43cd-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43cd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e43cd-123">See Also</span></span>  
 [<span data-ttu-id="e43cd-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e43cd-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="e43cd-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e43cd-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e43cd-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="e43cd-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
