---
title: COR_SEGMENT-Struktur
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 0370c74bde9ca5bdbd0fd03515f4b174ddd0a39a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132319"
---
# <a name="cor_segment-structure"></a><span data-ttu-id="4b93a-102">COR_SEGMENT-Struktur</span><span class="sxs-lookup"><span data-stu-id="4b93a-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="4b93a-103">Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="4b93a-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b93a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b93a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="4b93a-105">Member</span><span class="sxs-lookup"><span data-stu-id="4b93a-105">Members</span></span>  
  
|<span data-ttu-id="4b93a-106">Member</span><span class="sxs-lookup"><span data-stu-id="4b93a-106">Member</span></span>|<span data-ttu-id="4b93a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b93a-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="4b93a-108">Die Startadresse des Arbeitsspeicherbereichs</span><span class="sxs-lookup"><span data-stu-id="4b93a-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="4b93a-109">Die Endadresse des Arbeitsspeicherbereichs</span><span class="sxs-lookup"><span data-stu-id="4b93a-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="4b93a-110">Ein [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md)-Enumerationsmember, der die Generierung des Arbeitsspeicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="4b93a-110">A [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="4b93a-111">Die Nummer des Heaps, in dem sich der Arbeitsspeicherbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="4b93a-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="4b93a-112">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="4b93a-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b93a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b93a-113">Remarks</span></span>  
 <span data-ttu-id="4b93a-114">Die `COR_SEGMENTS`-Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.</span><span class="sxs-lookup"><span data-stu-id="4b93a-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="4b93a-115">`COR_SEGMENTS`-Objekte sind Member des Auflistungsobjekts [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), das durch einen Aufruf der Methode [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="4b93a-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="4b93a-116">Das `heap`-Feld ist die Nummer des Prozessors, der dem gemeldeten Heap entspricht.</span><span class="sxs-lookup"><span data-stu-id="4b93a-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="4b93a-117">Für Arbeitsstations-Garbage Collectors ist der Wert immer 0 (null), da Arbeitsstationen über nur einen Garbage Collection-Heap verfügen.</span><span class="sxs-lookup"><span data-stu-id="4b93a-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="4b93a-118">Für Server-Garbage Collectors entspricht der Wert dem Prozessor, an den der Heap angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="4b93a-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="4b93a-119">Beachten Sie, dass es aufgrund der Implementierungsdetails des Garbage Collectors mehr oder weniger Garbage Collection-Heaps als tatsächliche Prozessoren geben kann.</span><span class="sxs-lookup"><span data-stu-id="4b93a-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b93a-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b93a-120">Requirements</span></span>  
 <span data-ttu-id="4b93a-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b93a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b93a-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b93a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b93a-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b93a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b93a-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b93a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b93a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b93a-125">See also</span></span>

- [<span data-ttu-id="4b93a-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="4b93a-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4b93a-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4b93a-127">Debugging</span></span>](index.md)
