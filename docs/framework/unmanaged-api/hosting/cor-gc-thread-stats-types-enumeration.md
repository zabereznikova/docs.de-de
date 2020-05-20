---
title: COR_GC_THREAD_STATS_TYPES-Enumeration
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
ms.openlocfilehash: 2206499cad9be2a29f485ee66d468accbe00b5f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616677"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="74a9e-102">COR_GC_THREAD_STATS_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="74a9e-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="74a9e-103">Gibt die Garbage Collection Statistiken für einen Thread an.</span><span class="sxs-lookup"><span data-stu-id="74a9e-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74a9e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="74a9e-105">Member</span><span class="sxs-lookup"><span data-stu-id="74a9e-105">Members</span></span>  
  
|<span data-ttu-id="74a9e-106">Member</span><span class="sxs-lookup"><span data-stu-id="74a9e-106">Member</span></span>|<span data-ttu-id="74a9e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a9e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="74a9e-108">Der Thread verfügt über bytes, die im letzten Garbage Collection höher gestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="74a9e-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74a9e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74a9e-109">Requirements</span></span>  
 <span data-ttu-id="74a9e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74a9e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74a9e-111">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="74a9e-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="74a9e-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74a9e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a9e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a9e-113">See also</span></span>

- [<span data-ttu-id="74a9e-114">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="74a9e-114">Hosting Enumerations</span></span>](hosting-enumerations.md)
