---
title: COR_ARRAY_LAYOUT-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_ARRAY_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_ARRAY_LAYOUT
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 02ddd87cfaf16990ff487dfe27f30a2493cb9a01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="fb0cf-102">COR_ARRAY_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="fb0cf-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="fb0cf-103">Bietet Informationen zum Layout eines Arrayobjekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb0cf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="fb0cf-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb0cf-105">Members</span></span>  
  
|<span data-ttu-id="fb0cf-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb0cf-106">Member</span></span>|<span data-ttu-id="fb0cf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb0cf-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="fb0cf-108">Der Bezeichner des Typs von Objekten, die das Array enthält.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="fb0cf-109">Ein Wert der CorElementType-Enumeration, der angibt, ob die Komponente eine Garbage Collection-Verweis, eine Wertklasse oder ein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="fb0cf-110">Der Offset, der das erste Element im Array.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="fb0cf-111">Die Größe jedes Elements.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="fb0cf-112">Der Offset, der die Anzahl der Elemente im Array.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="fb0cf-113">Die Größe der Rang in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="fb0cf-114">Die Anzahl der Ränge im Array.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="fb0cf-115">Der Offset, an dem die Ränge starten.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb0cf-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb0cf-116">Remarks</span></span>  
 <span data-ttu-id="fb0cf-117">Die `rankSize` Feld gibt die Größe der Rang in ein mehrdimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="fb0cf-118">Für eindimensionale Arrays als auch präzise ist.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="fb0cf-119">Der Wert der `numRanks` ist 1 für ein eindimensionales Array und `N` für ein mehrdimensionales Array des `N` Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="fb0cf-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb0cf-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb0cf-120">Requirements</span></span>  
 <span data-ttu-id="fb0cf-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb0cf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb0cf-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb0cf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb0cf-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb0cf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb0cf-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb0cf-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0cf-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb0cf-125">See Also</span></span>  
 [<span data-ttu-id="fb0cf-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="fb0cf-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="fb0cf-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fb0cf-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
