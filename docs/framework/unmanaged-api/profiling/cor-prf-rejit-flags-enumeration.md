---
title: COR_PRF_REJIT_FLAGS-Enumeration
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974110"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="981d3-102">COR_PRF_REJIT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="981d3-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="981d3-103">Enthält Werte, die angeben, wie sich die [ICorProfilerInfo10:: requestrejitwithinliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) -API Verhalten soll.</span><span class="sxs-lookup"><span data-stu-id="981d3-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="981d3-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="981d3-105">Member</span><span class="sxs-lookup"><span data-stu-id="981d3-105">Members</span></span>  
  
|<span data-ttu-id="981d3-106">Member</span><span class="sxs-lookup"><span data-stu-id="981d3-106">Member</span></span>|<span data-ttu-id="981d3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981d3-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="981d3-108">Die Verwendung von rejitted-Methoden in anderen Methoden wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="981d3-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="981d3-109">Rufen `GetFunctionParameters` Sie Rückrufe für alle Methoden ab, die Inline-Methoden für die erneute kompizierer Anforderung angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="981d3-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="981d3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="981d3-110">Requirements</span></span>  
 <span data-ttu-id="981d3-111">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="981d3-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="981d3-112">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="981d3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="981d3-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="981d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="981d3-114">**.NET Framework-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="981d3-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="981d3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="981d3-115">See also</span></span>

- [<span data-ttu-id="981d3-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="981d3-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
