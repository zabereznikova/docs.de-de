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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179290"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="a22c2-102">COR_IL_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="a22c2-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="a22c2-103">Gibt Änderungen im relativen Offset einer Funktion an.</span><span class="sxs-lookup"><span data-stu-id="a22c2-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a22c2-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="a22c2-105">Members</span><span class="sxs-lookup"><span data-stu-id="a22c2-105">Members</span></span>  
  
|<span data-ttu-id="a22c2-106">Member</span><span class="sxs-lookup"><span data-stu-id="a22c2-106">Member</span></span>|<span data-ttu-id="a22c2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a22c2-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="a22c2-108">Der alte Microsoft-Zwischensprache (MSIL)-Offset relativ zum Anfang der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a22c2-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="a22c2-109">Der neue MSIL-Offset relativ zum Anfang der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a22c2-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="a22c2-110">`true`wenn die Zuordnung als korrekt bekannt ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="a22c2-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a22c2-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a22c2-111">Remarks</span></span>  
 <span data-ttu-id="a22c2-112">Das Format der Karte ist wie folgt: `oldOffset` Der Debugger geht davon aus, dass sich der MSIL-Offset innerhalb des ursprünglichen, unveränderten MSIL-Codes bezieht.</span><span class="sxs-lookup"><span data-stu-id="a22c2-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="a22c2-113">Der `newOffset` Parameter bezieht sich auf den entsprechenden MSIL-Offset innerhalb des neuen, instrumentierten Codes.</span><span class="sxs-lookup"><span data-stu-id="a22c2-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="a22c2-114">Damit das Schrittwerk ordnungsgemäß funktioniert, sollten die folgenden Anforderungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="a22c2-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="a22c2-115">Die Karte sollte in aufsteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="a22c2-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="a22c2-116">Instrumentierter MSIL-Code sollte nicht neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a22c2-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="a22c2-117">Der ursprüngliche MSIL-Code sollte nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="a22c2-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="a22c2-118">Die Karte sollte Einträge enthalten, um alle Sequenzpunkte aus der Programmdatenbankdatei (PDB) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a22c2-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="a22c2-119">Die Karte interpoliert keine fehlenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="a22c2-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="a22c2-120">Das folgende Beispiel zeigt eine Karte und ihre Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="a22c2-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="a22c2-121">Karte:</span><span class="sxs-lookup"><span data-stu-id="a22c2-121">Map:</span></span>  
  
- <span data-ttu-id="a22c2-122">0 alter Offset, 0 neuer Offset</span><span class="sxs-lookup"><span data-stu-id="a22c2-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="a22c2-123">5 alter Offset, 10 neuer Offset</span><span class="sxs-lookup"><span data-stu-id="a22c2-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="a22c2-124">9 alter Offset, 20 neuer Offset</span><span class="sxs-lookup"><span data-stu-id="a22c2-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="a22c2-125">Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="a22c2-125">Results:</span></span>  
  
- <span data-ttu-id="a22c2-126">Ein alter Offset von 0, 1, 2, 3 oder 4 wird einem neuen Offset von 0 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="a22c2-127">Ein alter Offset von 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="a22c2-128">Ein alter Offset von 9 oder höher wird dem neuen Offset 20 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="a22c2-129">Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="a22c2-130">Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="a22c2-131">Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a22c2-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a22c2-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a22c2-132">Requirements</span></span>  
 <span data-ttu-id="a22c2-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a22c2-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a22c2-134">**Kopfzeile:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a22c2-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="a22c2-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a22c2-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a22c2-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a22c2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22c2-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a22c2-137">See also</span></span>

- [<span data-ttu-id="a22c2-138">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="a22c2-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a22c2-139">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a22c2-139">Debugging</span></span>](index.md)
