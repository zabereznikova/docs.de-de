---
title: IGCHost::SetGCStartupLimits-Methode
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
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d99212b1ece4d3c0ce9440ac973b8254ebca6dde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="f08d8-102">IGCHost::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="f08d8-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="f08d8-103">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="f08d8-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f08d8-104">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], Sie können die Größe des Segments festlegen und die Größe von maximal Generation 0 zu Werte größer als `DWORD` mithilfe der [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f08d8-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f08d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f08d8-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f08d8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f08d8-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="f08d8-107">[in] Die Größe des Segments durch die Garbage Collection-System verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f08d8-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="f08d8-108">[in] Die maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="f08d8-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f08d8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f08d8-109">Remarks</span></span>  
 <span data-ttu-id="f08d8-110">Die `SetGCStartupLimits` -Methode nur einmal aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f08d8-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="f08d8-111">Diese Werte können später nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f08d8-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f08d8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f08d8-112">Requirements</span></span>  
 <span data-ttu-id="f08d8-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f08d8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f08d8-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="f08d8-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f08d8-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f08d8-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f08d8-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f08d8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08d8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f08d8-117">See Also</span></span>  
 [<span data-ttu-id="f08d8-118">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f08d8-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
