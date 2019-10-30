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
ms.openlocfilehash: b0fbc462283ef1577de8100e60fd09caa53db539
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131911"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="037f6-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="037f6-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="037f6-103">Gibt die Statistiken an, die für eine Garbage Collection aufgezeichnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="037f6-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="037f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="037f6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="037f6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="037f6-105">Remarks</span></span>  
 <span data-ttu-id="037f6-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur durch die [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) -Methode festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="037f6-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="037f6-107">Member</span><span class="sxs-lookup"><span data-stu-id="037f6-107">Members</span></span>  
  
|<span data-ttu-id="037f6-108">Member</span><span class="sxs-lookup"><span data-stu-id="037f6-108">Member</span></span>|<span data-ttu-id="037f6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="037f6-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="037f6-110">Zeichnet die Anzahl der Garbage Collections auf, die für jede Generation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="037f6-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="037f6-111">Zeichnet Statistiken zur Speicherauslastung und Garbage Collection Größe auf.</span><span class="sxs-lookup"><span data-stu-id="037f6-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="037f6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="037f6-112">Requirements</span></span>  
 <span data-ttu-id="037f6-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="037f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="037f6-114">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="037f6-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="037f6-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="037f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037f6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="037f6-116">See also</span></span>

- [<span data-ttu-id="037f6-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="037f6-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="037f6-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="037f6-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
