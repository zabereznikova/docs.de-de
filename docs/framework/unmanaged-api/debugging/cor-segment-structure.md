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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faf1be65d308b223490f3ae67eed3d8a2b1688b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223068"
---
# <a name="corsegment-structure"></a><span data-ttu-id="ef584-102">COR_SEGMENT-Struktur</span><span class="sxs-lookup"><span data-stu-id="ef584-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="ef584-103">Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="ef584-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef584-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef584-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="ef584-105">Member</span><span class="sxs-lookup"><span data-stu-id="ef584-105">Members</span></span>  
  
|<span data-ttu-id="ef584-106">Member</span><span class="sxs-lookup"><span data-stu-id="ef584-106">Member</span></span>|<span data-ttu-id="ef584-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef584-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="ef584-108">Die Startadresse des Arbeitsspeicherbereichs</span><span class="sxs-lookup"><span data-stu-id="ef584-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="ef584-109">Die Endadresse des Arbeitsspeicherbereichs</span><span class="sxs-lookup"><span data-stu-id="ef584-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="ef584-110">Ein [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)-Enumerationsmember, der die Generierung des Arbeitsspeicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef584-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="ef584-111">Die Nummer des Heaps, in dem sich der Arbeitsspeicherbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="ef584-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="ef584-112">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="ef584-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef584-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef584-113">Remarks</span></span>  
 <span data-ttu-id="ef584-114">Die `COR_SEGMENTS`-Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.</span><span class="sxs-lookup"><span data-stu-id="ef584-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  `COR_SEGMENTS` <span data-ttu-id="ef584-115">Objekte sind Mitglieder der [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Auflistungsobjekt, das durch den Aufruf ausgefüllt wird die [icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ef584-115">objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="ef584-116">Das `heap`-Feld ist die Nummer des Prozessors, der dem gemeldeten Heap entspricht.</span><span class="sxs-lookup"><span data-stu-id="ef584-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="ef584-117">Für Arbeitsstations-Garbage Collectors ist der Wert immer 0 (null), da Arbeitsstationen über nur einen Garbage Collection-Heap verfügen.</span><span class="sxs-lookup"><span data-stu-id="ef584-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="ef584-118">Für Server-Garbage Collectors entspricht der Wert dem Prozessor, an den der Heap angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="ef584-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="ef584-119">Beachten Sie, dass es aufgrund der Implementierungsdetails des Garbage Collectors mehr oder weniger Garbage Collection-Heaps als tatsächliche Prozessoren geben kann.</span><span class="sxs-lookup"><span data-stu-id="ef584-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef584-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef584-120">Requirements</span></span>  
 <span data-ttu-id="ef584-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef584-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef584-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef584-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef584-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef584-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ef584-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ef584-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef584-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef584-125">See also</span></span>

- [<span data-ttu-id="ef584-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ef584-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ef584-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ef584-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
