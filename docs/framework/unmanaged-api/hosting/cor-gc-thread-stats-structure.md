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
ms.openlocfilehash: 24a386fe82bbd004954924a573c090af7f58824a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431827"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="ce81b-102">COR_GC_THREAD_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="ce81b-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="ce81b-103">Enthält threadspezifische Statistiken zur Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="ce81b-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce81b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce81b-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="ce81b-105">Member</span><span class="sxs-lookup"><span data-stu-id="ce81b-105">Members</span></span>  
  
|<span data-ttu-id="ce81b-106">Member</span><span class="sxs-lookup"><span data-stu-id="ce81b-106">Member</span></span>|<span data-ttu-id="ce81b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce81b-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="ce81b-108">Die Anzahl der Bytes des Arbeitsspeichers für den Thread, die mit dem aktuellen anfallen `COR_GC_THREAD_STATS` Instanz.</span><span class="sxs-lookup"><span data-stu-id="ce81b-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="ce81b-109">Diese Zahl ist 0 (null) jedes Mal deaktiviert, tritt eine Generation 0 Garbagecollection auf.</span><span class="sxs-lookup"><span data-stu-id="ce81b-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="ce81b-110">Die Anzahl der Bytes, die auf eine höhere Generation der letzten Garbagecollection hochgestuft.</span><span class="sxs-lookup"><span data-stu-id="ce81b-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce81b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce81b-111">Remarks</span></span>  
 <span data-ttu-id="ce81b-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) akzeptiert einen Ausgabeparameter vom Typ `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="ce81b-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce81b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce81b-113">Requirements</span></span>  
 <span data-ttu-id="ce81b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce81b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce81b-115">**Header:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="ce81b-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="ce81b-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce81b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce81b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce81b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce81b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce81b-118">See Also</span></span>  
 [<span data-ttu-id="ce81b-119">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ce81b-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="ce81b-120">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce81b-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
