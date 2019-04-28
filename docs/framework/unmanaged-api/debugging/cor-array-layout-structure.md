---
title: COR_ARRAY_LAYOUT-Struktur
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a5a5bb26912c87cdf37ba0d8f0cee1cf1ffa97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609567"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="16bde-102">COR_ARRAY_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="16bde-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="16bde-103">Bietet Informationen zum Layout eines Arrayobjekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="16bde-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16bde-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16bde-104">Syntax</span></span>  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="16bde-105">Member</span><span class="sxs-lookup"><span data-stu-id="16bde-105">Members</span></span>  
  
|<span data-ttu-id="16bde-106">Member</span><span class="sxs-lookup"><span data-stu-id="16bde-106">Member</span></span>|<span data-ttu-id="16bde-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16bde-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="16bde-108">Der Bezeichner des Typs von Objekten, die das Array enthält.</span><span class="sxs-lookup"><span data-stu-id="16bde-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="16bde-109">Ein Wert der CorElementType-Enumeration, der angibt, ob die Komponente eine Garbage Collection-Verweis, eine Wertklasse oder ein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="16bde-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="16bde-110">Der Offset, der das erste Element im Array.</span><span class="sxs-lookup"><span data-stu-id="16bde-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="16bde-111">Die Größe der einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="16bde-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="16bde-112">Der Offset, der die Anzahl der Elemente im Array.</span><span class="sxs-lookup"><span data-stu-id="16bde-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="16bde-113">Die Größe des den Rang, wird in Bytes.</span><span class="sxs-lookup"><span data-stu-id="16bde-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="16bde-114">Die Anzahl der Ränge in das Array.</span><span class="sxs-lookup"><span data-stu-id="16bde-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="16bde-115">Der Offset, an dem die Ränge starten.</span><span class="sxs-lookup"><span data-stu-id="16bde-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16bde-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16bde-116">Remarks</span></span>  
 <span data-ttu-id="16bde-117">Die `rankSize` Feld gibt die Größe der Rang in ein mehrdimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="16bde-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="16bde-118">Es ist für eindimensionale Arrays auch präzise.</span><span class="sxs-lookup"><span data-stu-id="16bde-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="16bde-119">Der Wert des `numRanks` ist 1 für ein eindimensionales Array und `N` für ein mehrdimensionales Array des `N` Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="16bde-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16bde-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16bde-120">Requirements</span></span>  
 <span data-ttu-id="16bde-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16bde-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16bde-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16bde-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16bde-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16bde-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16bde-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16bde-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16bde-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16bde-125">See also</span></span>

- [<span data-ttu-id="16bde-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="16bde-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="16bde-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="16bde-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
