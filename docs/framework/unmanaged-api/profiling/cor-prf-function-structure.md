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
ms.openlocfilehash: 1bc8d588641163ccf98054fdf1930a72a04c770c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452061"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="6a02a-102">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="6a02a-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="6a02a-103">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="6a02a-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a02a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a02a-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="6a02a-105">Member</span><span class="sxs-lookup"><span data-stu-id="6a02a-105">Members</span></span>  
  
|<span data-ttu-id="6a02a-106">Member</span><span class="sxs-lookup"><span data-stu-id="6a02a-106">Member</span></span>|<span data-ttu-id="6a02a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a02a-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="6a02a-108">Die ID der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a02a-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="6a02a-109">Die ID der erneut kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a02a-109">The ID of the recompiled function.</span></span> <span data-ttu-id="6a02a-110">Der Wert 0 (null) darstellt, die ursprüngliche Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a02a-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a02a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a02a-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a02a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a02a-112">Requirements</span></span>  
 <span data-ttu-id="6a02a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a02a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a02a-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6a02a-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6a02a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a02a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a02a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a02a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a02a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a02a-117">See Also</span></span>  
 [<span data-ttu-id="6a02a-118">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6a02a-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
