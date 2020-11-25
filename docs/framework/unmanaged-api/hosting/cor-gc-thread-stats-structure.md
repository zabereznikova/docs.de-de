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
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699234"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="eefee-102">COR_GC_THREAD_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="eefee-102">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="eefee-103">Enthält Thread bezogene Statistiken für Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="eefee-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eefee-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="eefee-105">Member</span><span class="sxs-lookup"><span data-stu-id="eefee-105">Members</span></span>  
  
|<span data-ttu-id="eefee-106">Member</span><span class="sxs-lookup"><span data-stu-id="eefee-106">Member</span></span>|<span data-ttu-id="eefee-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eefee-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="eefee-108">Die Anzahl von Bytes im Arbeitsspeicher, die auf dem Thread zugeordnet ist, der der aktuellen Instanz zugeordnet ist `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="eefee-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="eefee-109">Diese Zahl wird bei jedem Garbage Collection der Generation 0 (null) auf 0 (null) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="eefee-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="eefee-110">Die Anzahl der Bytes, die bei der letzten Garbage Collection auf eine höhere Generation herauf gestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="eefee-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eefee-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eefee-111">Remarks</span></span>  

 <span data-ttu-id="eefee-112">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) nimmt einen Output-Parameter vom Typ an `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="eefee-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefee-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eefee-113">Requirements</span></span>  

 <span data-ttu-id="eefee-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefee-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefee-115">**Header:** Gchost. idl</span><span class="sxs-lookup"><span data-stu-id="eefee-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="eefee-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eefee-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eefee-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefee-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eefee-118">See also</span></span>

- [<span data-ttu-id="eefee-119">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="eefee-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="eefee-120">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eefee-120">IHostTask Interface</span></span>](ihosttask-interface.md)
