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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101724"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="d7171-102">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="d7171-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="d7171-103">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="d7171-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7171-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7171-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="d7171-105">Member</span><span class="sxs-lookup"><span data-stu-id="d7171-105">Members</span></span>  
  
|<span data-ttu-id="d7171-106">Member</span><span class="sxs-lookup"><span data-stu-id="d7171-106">Member</span></span>|<span data-ttu-id="d7171-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7171-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="d7171-108">Die ID der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d7171-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="d7171-109">Die ID der erneut kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="d7171-109">The ID of the recompiled function.</span></span> <span data-ttu-id="d7171-110">Der Wert 0 (null) stellt die ursprüngliche Version der Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="d7171-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7171-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7171-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7171-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7171-112">Requirements</span></span>  
 <span data-ttu-id="d7171-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7171-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7171-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d7171-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d7171-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7171-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d7171-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d7171-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7171-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7171-117">See also</span></span>

- [<span data-ttu-id="d7171-118">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d7171-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
