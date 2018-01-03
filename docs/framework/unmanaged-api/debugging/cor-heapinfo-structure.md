---
title: COR_HEAPINFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 991e018c3967693f5b87b71c77cdbadcd4ae0cfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="7a9a3-102">COR_HEAPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="7a9a3-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="7a9a3-103">Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a9a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a9a3-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7a9a3-105">Member</span><span class="sxs-lookup"><span data-stu-id="7a9a3-105">Members</span></span>  
  
|<span data-ttu-id="7a9a3-106">Member</span><span class="sxs-lookup"><span data-stu-id="7a9a3-106">Member</span></span>|<span data-ttu-id="7a9a3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a9a3-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="7a9a3-108">`true`Wenn die Garbage Collection-Strukturen gültig sind und der Heap aufgelistet werden kann; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="7a9a3-109">Die Größe in Bytes von Zeigern auf der Zielarchitektur.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="7a9a3-110">Die Anzahl der logischen Garbagecollection heaps im Prozess.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="7a9a3-111">`TRUE`Wenn die gleichzeitige Garbagecollection (im Hintergrund) aktiviert ist; andernfalls `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="7a9a3-112">Ein Mitglied der [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) -Enumeration, der angibt, ob die Garbage Collection auf einer Arbeitsstation oder einem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a9a3-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a9a3-113">Remarks</span></span>  
 <span data-ttu-id="7a9a3-114">Eine Instanz von der `COR_HEAPINFO` Struktur wird zurückgegeben, indem die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="7a9a3-115">Sie müssen immer überprüfen Sie vor dem Auflisten von Objekten auf dem Garbage Collection-Heap aus, die `areGCStructuresValid` Feld, um sicherzustellen, dass der Heap in einen enumerable-Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="7a9a3-116">Weitere Informationen finden Sie unter der [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7a9a3-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a9a3-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a9a3-117">Requirements</span></span>  
 <span data-ttu-id="7a9a3-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a9a3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a9a3-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a9a3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a9a3-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a9a3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a9a3-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a9a3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9a3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a9a3-122">See Also</span></span>  
 [<span data-ttu-id="7a9a3-123">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7a9a3-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="7a9a3-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7a9a3-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
