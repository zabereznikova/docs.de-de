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
ms.openlocfilehash: 18197f0c500a205a66bdda8a9401f31d4208ae67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780434"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="a49ff-102">COR_PRF_CLAUSE_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a49ff-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="a49ff-103">Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.</span><span class="sxs-lookup"><span data-stu-id="a49ff-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a49ff-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a49ff-105">Member</span><span class="sxs-lookup"><span data-stu-id="a49ff-105">Members</span></span>  
  
|<span data-ttu-id="a49ff-106">Member</span><span class="sxs-lookup"><span data-stu-id="a49ff-106">Member</span></span>|<span data-ttu-id="a49ff-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a49ff-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="a49ff-108">Die Exception-Klausel ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a49ff-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="a49ff-109">Die Exception-Klausel ist ein Filterausdruck.</span><span class="sxs-lookup"><span data-stu-id="a49ff-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="a49ff-110">Die Ausnahmeklausel ist ein `catch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a49ff-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="a49ff-111">Die Ausnahmeklausel ist ein `finally` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a49ff-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a49ff-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a49ff-112">Requirements</span></span>  
 <span data-ttu-id="a49ff-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a49ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a49ff-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a49ff-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a49ff-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a49ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a49ff-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a49ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49ff-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a49ff-117">See also</span></span>

- [<span data-ttu-id="a49ff-118">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="a49ff-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
