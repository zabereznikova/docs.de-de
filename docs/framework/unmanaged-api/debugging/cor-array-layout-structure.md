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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179352"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="c8355-102">COR_ARRAY_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="c8355-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="c8355-103">Bietet Informationen zum Layout eines Arrayobjekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="c8355-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8355-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8355-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c8355-105">Members</span><span class="sxs-lookup"><span data-stu-id="c8355-105">Members</span></span>  
  
|<span data-ttu-id="c8355-106">Member</span><span class="sxs-lookup"><span data-stu-id="c8355-106">Member</span></span>|<span data-ttu-id="c8355-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8355-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="c8355-108">Der Bezeichner des Objekttyps, den das Array enthält.</span><span class="sxs-lookup"><span data-stu-id="c8355-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="c8355-109">Ein CorElementType-Enumerationswert, der angibt, ob es sich bei der Komponente um einen Garbage Collection-Verweis, eine Wertklasse oder einen Primitiv handelt.</span><span class="sxs-lookup"><span data-stu-id="c8355-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="c8355-110">Der Offset zum ersten Element im Array.</span><span class="sxs-lookup"><span data-stu-id="c8355-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="c8355-111">Die Größe jedes Elements.</span><span class="sxs-lookup"><span data-stu-id="c8355-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="c8355-112">Der Offset zur Anzahl der Elemente im Array.</span><span class="sxs-lookup"><span data-stu-id="c8355-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="c8355-113">Die Größe des Rangs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c8355-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="c8355-114">Die Anzahl der Ränge im Array.</span><span class="sxs-lookup"><span data-stu-id="c8355-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="c8355-115">Der Offset, bei dem die Ränge beginnen.</span><span class="sxs-lookup"><span data-stu-id="c8355-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8355-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8355-116">Remarks</span></span>  
 <span data-ttu-id="c8355-117">Das `rankSize` Feld gibt die Größe eines Rangs in einem mehrdimensionalen Array an.</span><span class="sxs-lookup"><span data-stu-id="c8355-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="c8355-118">Es ist auch für eindimensionale Arrays genau.</span><span class="sxs-lookup"><span data-stu-id="c8355-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="c8355-119">Der Wert `numRanks` von ist 1 für `N` ein eindimensionales Array `N` und für ein mehrdimensionales Array von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="c8355-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8355-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8355-120">Requirements</span></span>  
 <span data-ttu-id="c8355-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8355-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8355-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8355-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8355-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8355-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8355-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8355-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8355-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8355-125">See also</span></span>

- [<span data-ttu-id="c8355-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c8355-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c8355-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c8355-127">Debugging</span></span>](index.md)
