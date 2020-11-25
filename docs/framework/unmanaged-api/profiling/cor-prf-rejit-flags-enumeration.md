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
ms.openlocfilehash: 09349674e0cf80649cc948e25a1c476c6f8097e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716368"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="9b146-102">COR_PRF_REJIT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b146-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="9b146-103">Enthält Werte, die angeben, wie sich die [ICorProfilerInfo10:: requestrejitwithinliners](icorprofilerinfo10-requestrejitwithinliners-method.md) -API Verhalten soll.</span><span class="sxs-lookup"><span data-stu-id="9b146-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b146-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b146-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9b146-105">Member</span><span class="sxs-lookup"><span data-stu-id="9b146-105">Members</span></span>  
  
|<span data-ttu-id="9b146-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b146-106">Member</span></span>|<span data-ttu-id="9b146-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b146-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="9b146-108">Die Verwendung von rejitted-Methoden in anderen Methoden wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="9b146-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="9b146-109">`GetFunctionParameters`Rufen Sie Rückrufe für alle Methoden ab, die Inline-Methoden für die erneute kompizierer Anforderung angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="9b146-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="9b146-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b146-110">Requirements</span></span>  

 <span data-ttu-id="9b146-111">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="9b146-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="9b146-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b146-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b146-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b146-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b146-114">**.NET Framework Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b146-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b146-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b146-115">See also</span></span>

- [<span data-ttu-id="9b146-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="9b146-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
