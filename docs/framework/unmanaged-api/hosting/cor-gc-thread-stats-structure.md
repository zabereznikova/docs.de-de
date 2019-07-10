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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f56ceca5269ebffb29908c63e698ce794027d8a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768062"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="4bac0-102">COR_GC_THREAD_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="4bac0-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="4bac0-103">Enthält pro-Thread-Statistiken, die Garbagecollection betreffen.</span><span class="sxs-lookup"><span data-stu-id="4bac0-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bac0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bac0-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="4bac0-105">Member</span><span class="sxs-lookup"><span data-stu-id="4bac0-105">Members</span></span>  
  
|<span data-ttu-id="4bac0-106">Member</span><span class="sxs-lookup"><span data-stu-id="4bac0-106">Member</span></span>|<span data-ttu-id="4bac0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bac0-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="4bac0-108">Die Anzahl der Bytes im Arbeitsspeicher reserviert, auf dem Thread, der mit dem aktuellen verknüpft ist `COR_GC_THREAD_STATS` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4bac0-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="4bac0-109">Diese Zahl ist 0 (null) bei jedem gelöscht eine Generation 0 Garbagecollection tritt auf.</span><span class="sxs-lookup"><span data-stu-id="4bac0-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="4bac0-110">Die Anzahl der Bytes, die auf eine höhere Generation für die automatische speicherbereinigung auf das neueste höher gestuft.</span><span class="sxs-lookup"><span data-stu-id="4bac0-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bac0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bac0-111">Remarks</span></span>  
 <span data-ttu-id="4bac0-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) nimmt einen Output-Parameter des Typs `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="4bac0-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bac0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bac0-113">Requirements</span></span>  
 <span data-ttu-id="4bac0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bac0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bac0-115">**Header:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="4bac0-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="4bac0-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4bac0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bac0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bac0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bac0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bac0-118">See also</span></span>

- [<span data-ttu-id="4bac0-119">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="4bac0-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="4bac0-120">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bac0-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
