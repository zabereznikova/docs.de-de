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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090354"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="acf4c-102">COR_HEAPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="acf4c-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="acf4c-103">Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.</span><span class="sxs-lookup"><span data-stu-id="acf4c-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acf4c-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="acf4c-105">Member</span><span class="sxs-lookup"><span data-stu-id="acf4c-105">Members</span></span>  
  
|<span data-ttu-id="acf4c-106">Member</span><span class="sxs-lookup"><span data-stu-id="acf4c-106">Member</span></span>|<span data-ttu-id="acf4c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acf4c-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="acf4c-108">`true` Wenn der Garbage Collection-Strukturen sind gültig und der Heap aufgelistet werden kann; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="acf4c-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="acf4c-109">Die Größe in Byte von Zeigern auf der Zielarchitektur.</span><span class="sxs-lookup"><span data-stu-id="acf4c-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="acf4c-110">Die Anzahl der logischen speicherbereinigung heaps im Prozess.</span><span class="sxs-lookup"><span data-stu-id="acf4c-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="acf4c-111">`TRUE` Wenn die gleichzeitige Garbagecollection (Hintergrund) aktiviert ist. andernfalls `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="acf4c-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="acf4c-112">Ein Mitglied der [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) Enumeration, der angibt, ob der Garbage Collection auf einer Arbeitsstation oder einem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="acf4c-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acf4c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acf4c-113">Remarks</span></span>  
 <span data-ttu-id="acf4c-114">Eine Instanz von der `COR_HEAPINFO` Struktur wird zurückgegeben, indem die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="acf4c-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="acf4c-115">Sie müssen immer überprüfen, vor der Enumeration von Objekten auf dem Garbage Collection-Heap, der `areGCStructuresValid` Feld, um sicherzustellen, dass der Heap aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="acf4c-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="acf4c-116">Weitere Informationen finden Sie unter den [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="acf4c-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf4c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acf4c-117">Requirements</span></span>  
 <span data-ttu-id="acf4c-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf4c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf4c-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acf4c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acf4c-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acf4c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acf4c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf4c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf4c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acf4c-122">See also</span></span>

- [<span data-ttu-id="acf4c-123">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="acf4c-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="acf4c-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="acf4c-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
