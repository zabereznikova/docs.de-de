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
ms.openlocfilehash: c3058229a3c2b3c529136dad70fea35a23708a33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718656"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="42386-102">COR_PRF_CLAUSE_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="42386-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>

<span data-ttu-id="42386-103">Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.</span><span class="sxs-lookup"><span data-stu-id="42386-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42386-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42386-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="42386-105">Member</span><span class="sxs-lookup"><span data-stu-id="42386-105">Members</span></span>  
  
|<span data-ttu-id="42386-106">Member</span><span class="sxs-lookup"><span data-stu-id="42386-106">Member</span></span>|<span data-ttu-id="42386-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42386-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="42386-108">Die Exception-Klausel ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="42386-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="42386-109">Die Exception-Klausel ist ein Filter Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="42386-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="42386-110">Die Exception-Klausel ist eine- `catch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="42386-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="42386-111">Die Exception-Klausel ist eine- `finally` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="42386-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42386-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42386-112">Requirements</span></span>  

 <span data-ttu-id="42386-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42386-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42386-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42386-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42386-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42386-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42386-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42386-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42386-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42386-117">See also</span></span>

- [<span data-ttu-id="42386-118">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="42386-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
