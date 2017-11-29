---
title: COR_PRF_FUNCTION-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION
helpviewer_keywords: COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b8ca316814b6f4df8792d068bea36d499b77374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunction-structure"></a><span data-ttu-id="f073f-102">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="f073f-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="f073f-103">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="f073f-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f073f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f073f-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="f073f-105">Member</span><span class="sxs-lookup"><span data-stu-id="f073f-105">Members</span></span>  
  
|<span data-ttu-id="f073f-106">Member</span><span class="sxs-lookup"><span data-stu-id="f073f-106">Member</span></span>|<span data-ttu-id="f073f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f073f-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="f073f-108">Die ID der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f073f-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="f073f-109">Die ID der erneut kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="f073f-109">The ID of the recompiled function.</span></span> <span data-ttu-id="f073f-110">Der Wert 0 (null) darstellt, die ursprüngliche Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f073f-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f073f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f073f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f073f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f073f-112">Requirements</span></span>  
 <span data-ttu-id="f073f-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f073f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f073f-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f073f-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f073f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f073f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f073f-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f073f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f073f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f073f-117">See Also</span></span>  
 [<span data-ttu-id="f073f-118">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f073f-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
