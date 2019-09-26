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
ms.openlocfilehash: f7b340a73aa9eaebca9c0d78563ae298557039b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274190"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="7b6d7-102">COR_HEAPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="7b6d7-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="7b6d7-103">Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b6d7-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7b6d7-105">Member</span><span class="sxs-lookup"><span data-stu-id="7b6d7-105">Members</span></span>  
  
|<span data-ttu-id="7b6d7-106">Member</span><span class="sxs-lookup"><span data-stu-id="7b6d7-106">Member</span></span>|<span data-ttu-id="7b6d7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b6d7-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="7b6d7-108">`true`, wenn Garbage Collection Strukturen gültig sind und der Heap aufgelistet werden kann. `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="7b6d7-109">Die Größe von Zeigern in der Zielarchitektur in Byte.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="7b6d7-110">Die Anzahl logischer Garbage Collection Heaps im Prozess.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="7b6d7-111">`TRUE`, wenn die gleichzeitige (Background-) Garbage Collection aktiviert ist. `FALSE`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="7b6d7-112">Ein Member der [cordebuggctype](cordebuggctype-enumeration.md) -Enumeration, der angibt, ob der Garbage Collector auf einer Arbeitsstation oder einem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b6d7-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b6d7-113">Remarks</span></span>  
 <span data-ttu-id="7b6d7-114">Eine Instanz der `COR_HEAPINFO` -Struktur wird durch Aufrufen der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="7b6d7-115">Vor dem Auflisten von Objekten auf dem Garbage Collection Heap muss immer das `areGCStructuresValid` Feld überprüft werden, um sicherzustellen, dass sich der Heap in einem Aufzähl Bare-Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="7b6d7-116">Weitere Informationen finden Sie unter der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="7b6d7-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b6d7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b6d7-117">Requirements</span></span>  
 <span data-ttu-id="7b6d7-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b6d7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b6d7-119">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="7b6d7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b6d7-120">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b6d7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b6d7-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6d7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6d7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b6d7-122">See also</span></span>

- [<span data-ttu-id="7b6d7-123">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7b6d7-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7b6d7-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7b6d7-124">Debugging</span></span>](index.md)
