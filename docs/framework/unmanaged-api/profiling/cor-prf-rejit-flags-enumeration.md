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
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177101"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="e8b26-102">COR_PRF_REJIT_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e8b26-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="e8b26-103">Enthält Werte, die angeben, wie sich die [ICorProfilerInfo10::RequestReJITWithInliners-API](icorprofilerinfo10-requestrejitwithinliners-method.md) verhalten soll.</span><span class="sxs-lookup"><span data-stu-id="e8b26-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8b26-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e8b26-105">Members</span><span class="sxs-lookup"><span data-stu-id="e8b26-105">Members</span></span>  
  
|<span data-ttu-id="e8b26-106">Member</span><span class="sxs-lookup"><span data-stu-id="e8b26-106">Member</span></span>|<span data-ttu-id="e8b26-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8b26-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="e8b26-108">ReJITted-Methoden werden daran gehindert, in andere Methoden einzufeinern.</span><span class="sxs-lookup"><span data-stu-id="e8b26-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="e8b26-109">Erhalten `GetFunctionParameters` Sie Rückrufe für alle Methoden, die die angeforderten Methoden inline inline.</span><span class="sxs-lookup"><span data-stu-id="e8b26-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="e8b26-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e8b26-110">Requirements</span></span>  
 <span data-ttu-id="e8b26-111">**Plattformen:** Siehe [.NET Core unterstützte Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e8b26-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="e8b26-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8b26-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8b26-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8b26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8b26-114">**.NET Framework-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b26-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8b26-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8b26-115">See also</span></span>

- [<span data-ttu-id="e8b26-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="e8b26-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
