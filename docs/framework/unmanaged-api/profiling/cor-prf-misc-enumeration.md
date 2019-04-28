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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599194"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="28a79-102">COR_PRF_MISC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="28a79-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="28a79-103">Enthält Konstantenwerte, die spezielle Bezeichner angeben.</span><span class="sxs-lookup"><span data-stu-id="28a79-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28a79-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="28a79-105">Member</span><span class="sxs-lookup"><span data-stu-id="28a79-105">Members</span></span>  
  
|<span data-ttu-id="28a79-106">Member</span><span class="sxs-lookup"><span data-stu-id="28a79-106">Member</span></span>|<span data-ttu-id="28a79-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28a79-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="28a79-108">Die Standard-ID ein, die [ICorProfilerInfo:: GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) für ein Modul, das noch nicht auf eine Assembly verbunden wurde.</span><span class="sxs-lookup"><span data-stu-id="28a79-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="28a79-109">Die Standard-Klassen-ID für globale Konstanten, die nicht zu einer Klasse gehören.</span><span class="sxs-lookup"><span data-stu-id="28a79-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="28a79-110">Der Modulbezeichner des standardmäßig für globale Objekte, die nicht auf ein Modul gehören.</span><span class="sxs-lookup"><span data-stu-id="28a79-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28a79-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28a79-111">Requirements</span></span>  
 <span data-ttu-id="28a79-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a79-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a79-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28a79-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28a79-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28a79-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28a79-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a79-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a79-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28a79-116">See also</span></span>

- [<span data-ttu-id="28a79-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="28a79-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
