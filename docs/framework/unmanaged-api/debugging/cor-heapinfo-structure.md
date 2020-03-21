---
title: COR_HEAPINFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179307"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="4803b-102">COR_HEAPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="4803b-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="4803b-103">Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.</span><span class="sxs-lookup"><span data-stu-id="4803b-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4803b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4803b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4803b-105">Members</span><span class="sxs-lookup"><span data-stu-id="4803b-105">Members</span></span>  
  
|<span data-ttu-id="4803b-106">Member</span><span class="sxs-lookup"><span data-stu-id="4803b-106">Member</span></span>|<span data-ttu-id="4803b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4803b-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="4803b-108">`true`wenn Garbage Collection-Strukturen gültig sind und der Heap aufgezählt werden kann; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="4803b-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="4803b-109">Die Größe von Zeigern auf die Zielarchitektur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4803b-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="4803b-110">Die Anzahl der logischen Garbage Collection-Heaps im Prozess.</span><span class="sxs-lookup"><span data-stu-id="4803b-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="4803b-111">`TRUE`wenn die gleichzeitige (Hintergrund-)Garbage Collection aktiviert ist; andernfalls `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="4803b-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="4803b-112">Ein Member der [CorDebugGCType-Enumeration,](cordebuggctype-enumeration.md) der angibt, ob der Garbage Collector auf einer Arbeitsstation oder einem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4803b-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4803b-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4803b-113">Remarks</span></span>  
 <span data-ttu-id="4803b-114">Eine Instanz `COR_HEAPINFO` der Struktur wird zurückgegeben, indem die [ICorDebugProcess5::GetGCHeapInformation-Methode](icordebugprocess5-getgcheapinformation-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4803b-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="4803b-115">Bevor Sie Objekte auf dem Garbage Collection-Heap aufzählen, müssen Sie das `areGCStructuresValid` Feld immer überprüfen, um sicherzustellen, dass sich der Heap in einem aufzählbaren Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="4803b-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="4803b-116">Weitere Informationen finden Sie in der [ICorDebugProcess5::GetGCHeapInformation-Methode.](icordebugprocess5-getgcheapinformation-method.md)</span><span class="sxs-lookup"><span data-stu-id="4803b-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4803b-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4803b-117">Requirements</span></span>  
 <span data-ttu-id="4803b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4803b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4803b-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4803b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4803b-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4803b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4803b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4803b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4803b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4803b-122">See also</span></span>

- [<span data-ttu-id="4803b-123">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="4803b-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4803b-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4803b-124">Debugging</span></span>](index.md)
