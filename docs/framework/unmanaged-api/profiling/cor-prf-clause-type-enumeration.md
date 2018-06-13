---
title: COR_PRF_CLAUSE_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6909fa426fa952c0918638f40a571393c651e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449932"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="c0d3d-102">COR_PRF_CLAUSE_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c0d3d-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="c0d3d-103">Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.</span><span class="sxs-lookup"><span data-stu-id="c0d3d-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0d3d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="c0d3d-105">Member</span><span class="sxs-lookup"><span data-stu-id="c0d3d-105">Members</span></span>  
  
|<span data-ttu-id="c0d3d-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0d3d-106">Member</span></span>|<span data-ttu-id="c0d3d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0d3d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="c0d3d-108">Die Ausnahmeklausel ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="c0d3d-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="c0d3d-109">Die Ausnahmeklausel ist ein Filterausdruck.</span><span class="sxs-lookup"><span data-stu-id="c0d3d-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="c0d3d-110">Die Ausnahmeklausel ist ein `catch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c0d3d-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="c0d3d-111">Die Ausnahmeklausel ist ein `finally` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c0d3d-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0d3d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0d3d-112">Requirements</span></span>  
 <span data-ttu-id="c0d3d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d3d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d3d-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0d3d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0d3d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0d3d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0d3d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d3d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d3d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0d3d-117">See Also</span></span>  
 [<span data-ttu-id="c0d3d-118">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="c0d3d-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
