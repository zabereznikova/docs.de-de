---
title: COR_GC_STAT_TYPES-Enumeration
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd12feb47352d9bb78aa8ef056072f9bdc6fba3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710325"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="9a65d-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9a65d-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="9a65d-103">Gibt an, die Statistiken für eine Garbagecollection aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9a65d-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a65d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a65d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="9a65d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a65d-105">Remarks</span></span>  
 <span data-ttu-id="9a65d-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) sind, dass die Struktur festgelegt werden, indem [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9a65d-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="9a65d-107">Member</span><span class="sxs-lookup"><span data-stu-id="9a65d-107">Members</span></span>  
  
|<span data-ttu-id="9a65d-108">Member</span><span class="sxs-lookup"><span data-stu-id="9a65d-108">Member</span></span>|<span data-ttu-id="9a65d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a65d-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="9a65d-110">Datensätze werden die Anzahl der Garbage Collections für jede Generierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9a65d-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="9a65d-111">Datensätze speicherauslastung und Garbage Collection Größe speicherstatistiken.</span><span class="sxs-lookup"><span data-stu-id="9a65d-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a65d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a65d-112">Requirements</span></span>  
 <span data-ttu-id="9a65d-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a65d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a65d-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="9a65d-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9a65d-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a65d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a65d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a65d-116">See also</span></span>
- [<span data-ttu-id="9a65d-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="9a65d-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="9a65d-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9a65d-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
