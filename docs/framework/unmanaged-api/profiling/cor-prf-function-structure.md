---
title: COR_PRF_FUNCTION-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14d42a4032c3e2b1c231414678912e1658e759d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101724"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="981de-102">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="981de-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="981de-103">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="981de-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="981de-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="981de-105">Member</span><span class="sxs-lookup"><span data-stu-id="981de-105">Members</span></span>  
  
|<span data-ttu-id="981de-106">Member</span><span class="sxs-lookup"><span data-stu-id="981de-106">Member</span></span>|<span data-ttu-id="981de-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981de-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="981de-108">Die ID der Funktion.</span><span class="sxs-lookup"><span data-stu-id="981de-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="981de-109">Die ID der erneut kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="981de-109">The ID of the recompiled function.</span></span> <span data-ttu-id="981de-110">Der Wert 0 (null) stellt die ursprüngliche Version der Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="981de-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="981de-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="981de-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="981de-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="981de-112">Requirements</span></span>  
 <span data-ttu-id="981de-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="981de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="981de-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="981de-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="981de-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="981de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="981de-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="981de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981de-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="981de-117">See also</span></span>

- [<span data-ttu-id="981de-118">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="981de-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
