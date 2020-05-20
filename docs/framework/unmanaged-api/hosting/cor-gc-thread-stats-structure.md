---
title: COR_GC_THREAD_STATS-Struktur
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616696"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="f35d2-102">COR_GC_THREAD_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="f35d2-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="f35d2-103">Enthält Thread bezogene Statistiken für Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f35d2-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f35d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f35d2-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="f35d2-105">Member</span><span class="sxs-lookup"><span data-stu-id="f35d2-105">Members</span></span>  
  
|<span data-ttu-id="f35d2-106">Member</span><span class="sxs-lookup"><span data-stu-id="f35d2-106">Member</span></span>|<span data-ttu-id="f35d2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f35d2-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="f35d2-108">Die Anzahl von Bytes im Arbeitsspeicher, die auf dem Thread zugeordnet ist, der der aktuellen Instanz zugeordnet ist `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="f35d2-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="f35d2-109">Diese Zahl wird bei jedem Garbage Collection der Generation 0 (null) auf 0 (null) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f35d2-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="f35d2-110">Die Anzahl der Bytes, die bei der letzten Garbage Collection auf eine höhere Generation herauf gestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="f35d2-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f35d2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f35d2-111">Remarks</span></span>  
 <span data-ttu-id="f35d2-112">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) nimmt einen Output-Parameter vom Typ an `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="f35d2-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f35d2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f35d2-113">Requirements</span></span>  
 <span data-ttu-id="f35d2-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f35d2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f35d2-115">**Header:** Gchost. idl</span><span class="sxs-lookup"><span data-stu-id="f35d2-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="f35d2-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f35d2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f35d2-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f35d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35d2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f35d2-118">See also</span></span>

- [<span data-ttu-id="f35d2-119">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="f35d2-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="f35d2-120">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f35d2-120">IHostTask Interface</span></span>](ihosttask-interface.md)
