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
ms.openlocfilehash: 6fdfe33c5b488d8f464001a86233124d4e7df0ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779068"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="153b7-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="153b7-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="153b7-103">Gibt an, die Statistiken für eine Garbagecollection aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="153b7-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="153b7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="153b7-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="153b7-105">Remarks</span></span>  
 <span data-ttu-id="153b7-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) sind, dass die Struktur festgelegt werden, indem [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="153b7-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="153b7-107">Member</span><span class="sxs-lookup"><span data-stu-id="153b7-107">Members</span></span>  
  
|<span data-ttu-id="153b7-108">Member</span><span class="sxs-lookup"><span data-stu-id="153b7-108">Member</span></span>|<span data-ttu-id="153b7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="153b7-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="153b7-110">Datensätze werden die Anzahl der Garbage Collections für jede Generierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="153b7-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="153b7-111">Datensätze speicherauslastung und Garbage Collection Größe speicherstatistiken.</span><span class="sxs-lookup"><span data-stu-id="153b7-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="153b7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="153b7-112">Requirements</span></span>  
 <span data-ttu-id="153b7-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="153b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="153b7-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="153b7-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="153b7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="153b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153b7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="153b7-116">See also</span></span>

- [<span data-ttu-id="153b7-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="153b7-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="153b7-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="153b7-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
