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
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687872"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="333fd-102">IGCHost::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="333fd-102">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="333fd-103">Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="333fd-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="333fd-104">Beginnend mit dem .NET Framework 4,5 können Sie die Segmentgröße und die maximale Generation 0-Größe auf Werte festlegen, die größer als sind, `DWORD` indem Sie die [IGCHost2:: setgcstartuplimitsex](igchost2-setgcstartuplimitsex-method.md) -Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="333fd-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="333fd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="333fd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="333fd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="333fd-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="333fd-107">in Die Größe des Segments, das vom Garbage Collection System verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="333fd-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="333fd-108">in Die maximale Größe für die Generation 0.</span><span class="sxs-lookup"><span data-stu-id="333fd-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="333fd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="333fd-109">Remarks</span></span>  

 <span data-ttu-id="333fd-110">Die- `SetGCStartupLimits` Methode kann nur einmal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="333fd-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="333fd-111">Diese Werte können später nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="333fd-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="333fd-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="333fd-112">Requirements</span></span>  

 <span data-ttu-id="333fd-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="333fd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="333fd-114">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="333fd-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="333fd-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="333fd-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="333fd-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="333fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333fd-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="333fd-117">See also</span></span>

- [<span data-ttu-id="333fd-118">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="333fd-118">IGCHost Interface</span></span>](igchost-interface.md)
