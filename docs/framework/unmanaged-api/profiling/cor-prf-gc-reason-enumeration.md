---
title: COR_PRF_GC_REASON-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
ms.openlocfilehash: f10ec279e67b86448298745a488f5b3e833e8c39
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447371"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="aec2a-102">COR_PRF_GC_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="aec2a-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="aec2a-103">Zeigt den Grund, weshalb die Garbage Collection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="aec2a-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aec2a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="aec2a-105">Member</span><span class="sxs-lookup"><span data-stu-id="aec2a-105">Members</span></span>  
  
|<span data-ttu-id="aec2a-106">Member</span><span class="sxs-lookup"><span data-stu-id="aec2a-106">Member</span></span>|<span data-ttu-id="aec2a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aec2a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="aec2a-108">Der Garbage Collection wurde durch eine <xref:System.GC.Collect%2A> Methode ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="aec2a-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="aec2a-109">Der Grund ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="aec2a-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aec2a-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aec2a-110">Requirements</span></span>  
 <span data-ttu-id="aec2a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec2a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec2a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aec2a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aec2a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aec2a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aec2a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec2a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aec2a-115">See also</span></span>

- [<span data-ttu-id="aec2a-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="aec2a-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
