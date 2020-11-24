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
ms.openlocfilehash: 1da8f414ccf0c1eed3ec7dde842dd381440a3fa9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674956"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="f444c-102">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="f444c-102">COR_PRF_FUNCTION Structure</span></span>

<span data-ttu-id="f444c-103">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="f444c-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f444c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f444c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="f444c-105">Member</span><span class="sxs-lookup"><span data-stu-id="f444c-105">Members</span></span>  
  
|<span data-ttu-id="f444c-106">Member</span><span class="sxs-lookup"><span data-stu-id="f444c-106">Member</span></span>|<span data-ttu-id="f444c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f444c-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="f444c-108">Die ID der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f444c-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="f444c-109">Die ID der neu kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="f444c-109">The ID of the recompiled function.</span></span> <span data-ttu-id="f444c-110">Der Wert 0 (null) stellt die ursprüngliche Version der Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="f444c-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f444c-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f444c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f444c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f444c-112">Requirements</span></span>  

 <span data-ttu-id="f444c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f444c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f444c-114">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="f444c-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f444c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f444c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f444c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f444c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f444c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f444c-117">See also</span></span>

- [<span data-ttu-id="f444c-118">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f444c-118">Profiling Structures</span></span>](profiling-structures.md)
