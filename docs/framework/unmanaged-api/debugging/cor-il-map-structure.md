---
title: COR_IL_MAP-Struktur
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74f515626f5001cbea1a25e8268338c588524bde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740534"
---
# <a name="corilmap-structure"></a><span data-ttu-id="2ab01-102">COR_IL_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="2ab01-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="2ab01-103">Gibt Änderungen im relativen Offset einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="2ab01-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ab01-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="2ab01-105">Member</span><span class="sxs-lookup"><span data-stu-id="2ab01-105">Members</span></span>  
  
|<span data-ttu-id="2ab01-106">Member</span><span class="sxs-lookup"><span data-stu-id="2ab01-106">Member</span></span>|<span data-ttu-id="2ab01-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab01-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="2ab01-108">Die alten Microsoft intermediate Language (MSIL) offset relativ zum Anfang der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ab01-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="2ab01-109">Der neue MSIL-Offset relativ zum Anfang der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ab01-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="2ab01-110">`true` Wenn die Zuordnung als genau bekannt wird; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2ab01-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab01-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ab01-111">Remarks</span></span>  
 <span data-ttu-id="2ab01-112">Das Format der Karte sieht folgendermaßen aus: Der Debugger geht davon aus, die `oldOffset` verweist auf einen MSIL-Offset innerhalb der ursprünglichen, unveränderten MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="2ab01-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="2ab01-113">Die `newOffset` Parameter verweist auf die entsprechenden MSIL-Offset innerhalb der neuen, instrumentierten Code.</span><span class="sxs-lookup"><span data-stu-id="2ab01-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="2ab01-114">Für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten, sollten die folgenden Anforderungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="2ab01-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="2ab01-115">Die Karte sollten in aufsteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="2ab01-116">Instrumentierter MSIL-Code muss nicht neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="2ab01-117">Ursprüngliche MSIL-Code sollte nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="2ab01-118">Die Zuordnung sollte Einträge zum Zuordnen der Sequenzpunkte über die Programmdatenbankdatei (PDB) enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ab01-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="2ab01-119">Die Zuordnung wird nicht fehlenden Einträge interpoliert.</span><span class="sxs-lookup"><span data-stu-id="2ab01-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="2ab01-120">Das folgende Beispiel zeigt eine Zuordnung und ihre Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2ab01-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="2ab01-121">Ordnen Sie:</span><span class="sxs-lookup"><span data-stu-id="2ab01-121">Map:</span></span>  
  
- <span data-ttu-id="2ab01-122">0 alte Offset, 0 neue offset</span><span class="sxs-lookup"><span data-stu-id="2ab01-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="2ab01-123">5 alte Offset, 10 neuen offset</span><span class="sxs-lookup"><span data-stu-id="2ab01-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="2ab01-124">9 alte Offset, 20 neue offset</span><span class="sxs-lookup"><span data-stu-id="2ab01-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="2ab01-125">Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="2ab01-125">Results:</span></span>  
  
- <span data-ttu-id="2ab01-126">Ein Alter Offset von 0, 1, 2, 3 oder 4 wird ein neuer Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="2ab01-127">Ein Alter Offset von 5, 6, 7 oder 8 wird zum neuen Offset 10 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="2ab01-128">Ein Alter Offset des 9 oder höher wird zum neuen Offset 20 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="2ab01-129">Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 werden alte Offset 0 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="2ab01-130">Alte Offset 5 wird ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="2ab01-131">Ein neuer Offset von 20 oder höher werden alte Offset 9 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab01-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab01-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ab01-132">Requirements</span></span>  
 <span data-ttu-id="2ab01-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab01-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab01-134">**Header:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2ab01-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="2ab01-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ab01-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ab01-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab01-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab01-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ab01-137">See also</span></span>

- [<span data-ttu-id="2ab01-138">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="2ab01-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2ab01-139">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2ab01-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
