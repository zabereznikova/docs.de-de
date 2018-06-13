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
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406506"
---
# <a name="corsegment-structure"></a><span data-ttu-id="22e77-102">COR_SEGMENT-Struktur</span><span class="sxs-lookup"><span data-stu-id="22e77-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="22e77-103">Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="22e77-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22e77-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="22e77-105">Member</span><span class="sxs-lookup"><span data-stu-id="22e77-105">Members</span></span>  
  
|<span data-ttu-id="22e77-106">Member</span><span class="sxs-lookup"><span data-stu-id="22e77-106">Member</span></span>|<span data-ttu-id="22e77-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22e77-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="22e77-108">Die Startadresse des Arbeitsspeicherbereichs.</span><span class="sxs-lookup"><span data-stu-id="22e77-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="22e77-109">Die Endadresse für den Speicherbereich.</span><span class="sxs-lookup"><span data-stu-id="22e77-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="22e77-110">Ein [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) Enumerationsmember, der die Generierung von den Speicherbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="22e77-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="22e77-111">Die Heap-Anzahl in der der Speicherbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="22e77-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="22e77-112">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="22e77-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22e77-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22e77-113">Remarks</span></span>  
 <span data-ttu-id="22e77-114">Die `COR_SEGMENTS` -Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.</span><span class="sxs-lookup"><span data-stu-id="22e77-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="22e77-115">`COR_SEGMENTS` Objekte sind Mitglieder der [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Auflistungsobjekt, das durch Aufrufen von Werten aufgefüllt ist die[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="22e77-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="22e77-116">Die `heap` Feld wird die Prozessor-Zahl, die dem Heap gemeldet wird entspricht.</span><span class="sxs-lookup"><span data-stu-id="22e77-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="22e77-117">Für die Arbeitsstation Garbage Collectors ist der Wert immer 0 (null), Schreibberechtigung Arbeitsstationen nur eine Garbage Collection-Heap an.</span><span class="sxs-lookup"><span data-stu-id="22e77-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="22e77-118">Für Server-Garbage Collectors entspricht der Wert der Prozessor, dem der Heap zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="22e77-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="22e77-119">Beachten Sie, dass möglicherweise mehr oder weniger Garbagecollection heaps als tatsächliche Prozessoren aufgrund von den Implementierungsdetails der Garbage Collector vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="22e77-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22e77-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22e77-120">Requirements</span></span>  
 <span data-ttu-id="22e77-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22e77-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22e77-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22e77-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22e77-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22e77-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22e77-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22e77-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e77-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22e77-125">See Also</span></span>  
 [<span data-ttu-id="22e77-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="22e77-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="22e77-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="22e77-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
