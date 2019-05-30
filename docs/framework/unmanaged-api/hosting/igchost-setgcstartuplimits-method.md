---
title: IGCHost::SetGCStartupLimits-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e65a83d1da0580436babd15e4f27e2db7a698668
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377610"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="a96b5-102">IGCHost::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="a96b5-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="a96b5-103">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="a96b5-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a96b5-104">Ab .NET Framework 4.5, Sie können festlegen Segmentgröße und Größe von maximal Generation 0 zu Werten größer als `DWORD` mithilfe der [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="a96b5-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a96b5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a96b5-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a96b5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a96b5-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="a96b5-107">[in] Die Größe des Segments, die von der Garbage Collection-System verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a96b5-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="a96b5-108">[in] Die maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="a96b5-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a96b5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a96b5-109">Remarks</span></span>  
 <span data-ttu-id="a96b5-110">Die `SetGCStartupLimits` Methode nur einmal aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a96b5-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="a96b5-111">Diese Werte können nicht später geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a96b5-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a96b5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a96b5-112">Requirements</span></span>  
 <span data-ttu-id="a96b5-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a96b5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a96b5-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="a96b5-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a96b5-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a96b5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a96b5-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a96b5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a96b5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a96b5-117">See also</span></span>

- [<span data-ttu-id="a96b5-118">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a96b5-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
