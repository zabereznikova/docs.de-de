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
ms.openlocfilehash: ca9566168b8aae361af8d61539066624697a2d04
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805158"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="e408f-102">IGCHost2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="e408f-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="e408f-103">Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="e408f-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e408f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e408f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e408f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e408f-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="e408f-106">in Die Größe des Segments, das vom Garbage Collection System verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e408f-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="e408f-107">in Die maximale Größe für die Generation 0.</span><span class="sxs-lookup"><span data-stu-id="e408f-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e408f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e408f-108">Remarks</span></span>  
 <span data-ttu-id="e408f-109">Die Werte, die von `SetGCStartupLimitsEx` festgelegt werden, können nur angegeben werden, bevor der Host gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e408f-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="e408f-110">Diese Werte können später nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e408f-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e408f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e408f-111">Requirements</span></span>  
 <span data-ttu-id="e408f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e408f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e408f-113">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="e408f-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e408f-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e408f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e408f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e408f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e408f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e408f-116">See also</span></span>

- [<span data-ttu-id="e408f-117">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e408f-117">IGCHost2 Interface</span></span>](igchost2-interface.md)
