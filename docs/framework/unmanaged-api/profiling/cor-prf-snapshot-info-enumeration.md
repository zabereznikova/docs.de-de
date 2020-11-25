---
title: COR_PRF_SNAPSHOT_INFO-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 5290db008bfe5727ed5899c2ed6f7e41ae9a353a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716355"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="3909e-102">COR_PRF_SNAPSHOT_INFO-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3909e-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>

<span data-ttu-id="3909e-103">Gibt an, wie viele Daten bei jedem Abruf der [StackSnapshotCallback](stacksnapshotcallback-function.md) -Funktion des Profilers mit einer Stapel Momentaufnahme zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3909e-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3909e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3909e-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3909e-105">Member</span><span class="sxs-lookup"><span data-stu-id="3909e-105">Members</span></span>  
  
|<span data-ttu-id="3909e-106">Member</span><span class="sxs-lookup"><span data-stu-id="3909e-106">Members</span></span>|<span data-ttu-id="3909e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3909e-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="3909e-108">Gibt an, dass Werte für alle Parameter übergeben werden müssen `StackSnapshotCallback` , mit Ausnahme des- `context` Parameters.</span><span class="sxs-lookup"><span data-stu-id="3909e-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="3909e-109">Gibt an, dass Werte für alle `StackSnapshotCallback` Parameter, einschließlich des-Parameters, übergeben werden müssen `context` .</span><span class="sxs-lookup"><span data-stu-id="3909e-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="3909e-110">Gibt an, dass ein einfacherer, alternativer Stapel gehenden Algorithmus verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3909e-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3909e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3909e-111">Remarks</span></span>  

 <span data-ttu-id="3909e-112">Werte, die von der-Enumeration bereitgestellt werden, `COR_PRF_SNAPSHOT_INFO` werden als Parameter an die [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="3909e-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3909e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3909e-113">Requirements</span></span>  

 <span data-ttu-id="3909e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3909e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3909e-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3909e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3909e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3909e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3909e-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3909e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3909e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3909e-118">See also</span></span>

- [<span data-ttu-id="3909e-119">DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="3909e-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="3909e-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="3909e-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
