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
ms.openlocfilehash: c14e27b67fc600e2684f8c967af30bb9a5cee126
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716738"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="0be69-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0be69-102">COR_GC_STAT_TYPES Enumeration</span></span>

<span data-ttu-id="0be69-103">Gibt die Statistiken an, die für eine Garbage Collection aufgezeichnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0be69-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0be69-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="0be69-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0be69-105">Remarks</span></span>  

 <span data-ttu-id="0be69-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](cor-gc-stats-structure.md) Struktur von der [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md) -Methode festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0be69-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="0be69-107">Member</span><span class="sxs-lookup"><span data-stu-id="0be69-107">Members</span></span>  
  
|<span data-ttu-id="0be69-108">Member</span><span class="sxs-lookup"><span data-stu-id="0be69-108">Member</span></span>|<span data-ttu-id="0be69-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0be69-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="0be69-110">Zeichnet die Anzahl der Garbage Collections auf, die für jede Generation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0be69-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="0be69-111">Zeichnet Statistiken zur Speicherauslastung und Garbage Collection Größe auf.</span><span class="sxs-lookup"><span data-stu-id="0be69-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0be69-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0be69-112">Requirements</span></span>  

 <span data-ttu-id="0be69-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be69-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be69-114">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="0be69-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0be69-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be69-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be69-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0be69-116">See also</span></span>

- [<span data-ttu-id="0be69-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="0be69-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="0be69-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0be69-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
