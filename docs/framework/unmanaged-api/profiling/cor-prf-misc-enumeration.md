---
title: COR_PRF_MISC-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 5a3c820b52ae9376d769ea9956edc0b8553a1f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682171"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="b160a-102">COR_PRF_MISC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b160a-102">COR_PRF_MISC Enumeration</span></span>

<span data-ttu-id="b160a-103">Enthält Konstantenwerte, die spezielle Bezeichner angeben.</span><span class="sxs-lookup"><span data-stu-id="b160a-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b160a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b160a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="b160a-105">Member</span><span class="sxs-lookup"><span data-stu-id="b160a-105">Members</span></span>  
  
|<span data-ttu-id="b160a-106">Member</span><span class="sxs-lookup"><span data-stu-id="b160a-106">Member</span></span>|<span data-ttu-id="b160a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b160a-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="b160a-108">Der von [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) verwendete Standard Bezeichner für ein Modul, das noch nicht an eine Assembly angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="b160a-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="b160a-109">Der Standardklassen Bezeichner für globale Konstanten, die keiner Klasse angehören.</span><span class="sxs-lookup"><span data-stu-id="b160a-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="b160a-110">Der Standardmodul Bezeichner für globale Objekte, die nicht zu einem Modul gehören.</span><span class="sxs-lookup"><span data-stu-id="b160a-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b160a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b160a-111">Requirements</span></span>  

 <span data-ttu-id="b160a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b160a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b160a-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b160a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b160a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b160a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b160a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b160a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b160a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b160a-116">See also</span></span>

- [<span data-ttu-id="b160a-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="b160a-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
