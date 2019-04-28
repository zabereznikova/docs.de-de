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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa85fb2cebb47ecbd7b0f091cb79f6ea0936b1cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598999"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="e2c4b-102">COR_PRF_SNAPSHOT_INFO-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e2c4b-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="e2c4b-103">Gibt an, wie viel zu übergebende Daten mit einer Stapelmomentaufnahme in jedem Aufruf des Profilers Sichern [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2c4b-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e2c4b-105">Member</span><span class="sxs-lookup"><span data-stu-id="e2c4b-105">Members</span></span>  
  
|<span data-ttu-id="e2c4b-106">Member</span><span class="sxs-lookup"><span data-stu-id="e2c4b-106">Members</span></span>|<span data-ttu-id="e2c4b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2c4b-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="e2c4b-108">Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parameter, mit Ausnahme der `context` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="e2c4b-109">Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parametern – einschließlich der `context` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="e2c4b-110">Gibt an, dass ein einfacher, alternativer Stackwalk Algorithmus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2c4b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2c4b-111">Remarks</span></span>  
 <span data-ttu-id="e2c4b-112">Werte, die von bereitgestellten der `COR_PRF_SNAPSHOT_INFO` -Enumeration als Parameter übergeben werden die [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2c4b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2c4b-113">Requirements</span></span>  
 <span data-ttu-id="e2c4b-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2c4b-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2c4b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2c4b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2c4b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2c4b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2c4b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c4b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2c4b-118">See also</span></span>

- [<span data-ttu-id="e2c4b-119">DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="e2c4b-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="e2c4b-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="e2c4b-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
