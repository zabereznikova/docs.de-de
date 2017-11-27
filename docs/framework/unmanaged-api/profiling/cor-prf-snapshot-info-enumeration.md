---
title: COR_PRF_SNAPSHOT_INFO-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SNAPSHOT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SNAPSHOT_INFO
helpviewer_keywords: COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9c854360881426f2fc7fc9e401da1dc93b9bd84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="885a5-102">COR_PRF_SNAPSHOT_INFO-Enumeration</span><span class="sxs-lookup"><span data-stu-id="885a5-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="885a5-103">Gibt an, wie viel Sichern von Daten an, mit einer Stapelmomentaufnahme bei jedem Aufruf an des Profilers [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="885a5-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="885a5-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="885a5-105">Member</span><span class="sxs-lookup"><span data-stu-id="885a5-105">Members</span></span>  
  
|<span data-ttu-id="885a5-106">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="885a5-106">Members</span></span>|<span data-ttu-id="885a5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="885a5-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="885a5-108">Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parameter, mit Ausnahme der `context` Parameter.</span><span class="sxs-lookup"><span data-stu-id="885a5-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="885a5-109">Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parameter, einschließlich der `context` Parameter.</span><span class="sxs-lookup"><span data-stu-id="885a5-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="885a5-110">Gibt an, dass ein einfacherer und alternativer Stackwalk Algorithmus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="885a5-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="885a5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="885a5-111">Remarks</span></span>  
 <span data-ttu-id="885a5-112">Werte, die von bereitgestellt werden die `COR_PRF_SNAPSHOT_INFO` -Enumeration als Parameter übergeben werden die [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="885a5-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885a5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="885a5-113">Requirements</span></span>  
 <span data-ttu-id="885a5-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="885a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885a5-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="885a5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="885a5-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885a5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885a5-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885a5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885a5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="885a5-118">See Also</span></span>  
 [<span data-ttu-id="885a5-119">DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="885a5-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="885a5-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="885a5-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
