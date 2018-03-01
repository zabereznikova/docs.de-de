---
title: COR_GC_STAT_TYPES-Enumeration
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
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86d0ce931518fa50dbd3b0d6d7f2755d19042eca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="99750-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="99750-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="99750-103">Gibt an, die Statistiken für eine Garbagecollection aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="99750-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99750-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99750-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="99750-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99750-105">Remarks</span></span>  
 <span data-ttu-id="99750-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) Struktur sind, festgelegt werden, indem [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="99750-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="99750-107">Member</span><span class="sxs-lookup"><span data-stu-id="99750-107">Members</span></span>  
  
|<span data-ttu-id="99750-108">Member</span><span class="sxs-lookup"><span data-stu-id="99750-108">Member</span></span>|<span data-ttu-id="99750-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99750-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="99750-110">Datensätze werden die Anzahl der Garbage Collections für jede Generierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99750-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="99750-111">Datensätze einer speicherauslastung und Garbage Collection Größe Speicherstatistik.</span><span class="sxs-lookup"><span data-stu-id="99750-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99750-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99750-112">Requirements</span></span>  
 <span data-ttu-id="99750-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99750-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99750-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="99750-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="99750-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99750-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99750-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99750-116">See Also</span></span>  
 [<span data-ttu-id="99750-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="99750-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="99750-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="99750-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
