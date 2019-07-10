---
title: IGCHost2::SetGCStartupLimitsEx-Methode
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e834042c5e00709fcb2198c1496a8a630841d069
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779541"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="b4ca4-102">IGCHost2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="b4ca4-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="b4ca4-103">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="b4ca4-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ca4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4ca4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ca4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4ca4-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="b4ca4-106">[in] Die Größe des Segments, die von der Garbage Collection-System verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4ca4-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b4ca4-107">[in] Die maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="b4ca4-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4ca4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4ca4-108">Remarks</span></span>  
 <span data-ttu-id="b4ca4-109">Die Werte, die `SetGCStartupLimitsEx` legt können angegeben werden, nur verwendet werden, bevor der Host gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b4ca4-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="b4ca4-110">Diese Werte können nicht später geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b4ca4-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ca4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4ca4-111">Requirements</span></span>  
 <span data-ttu-id="b4ca4-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ca4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ca4-113">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b4ca4-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b4ca4-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4ca4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4ca4-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ca4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ca4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4ca4-116">See also</span></span>

- [<span data-ttu-id="b4ca4-117">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4ca4-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
