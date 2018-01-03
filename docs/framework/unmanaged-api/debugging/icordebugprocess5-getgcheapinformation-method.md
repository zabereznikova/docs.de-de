---
title: ICorDebugProcess5::GetGCHeapInformation-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetGCHeapInformation
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70e9e3ab6c7332e492b7146e52e0265653803bf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="c541c-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="c541c-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="c541c-103">Allgemeine Informationen zum Garbage Collection-Heap, z. B. ob er derzeit aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="c541c-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c541c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c541c-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c541c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c541c-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="c541c-106">[out] Ein Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Werte, die allgemeine Informationen zum Garbage Collection-Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c541c-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c541c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c541c-107">Remarks</span></span>  
 <span data-ttu-id="c541c-108">Die `ICorDebugProcess5::GetGCHeapInformation` Methode muss aufgerufen werden, bevor beim Aufzählen der Heap oder einzelne Heap Regionen, um sicherzustellen, dass die Garbagecollection-im Prozess Strukturen derzeit gültig sind.</span><span class="sxs-lookup"><span data-stu-id="c541c-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="c541c-109">Garbage Collection-Heap kann nicht durchlaufen werden soll, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c541c-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="c541c-110">Andernfalls kann die Enumeration Garbage Collection-Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="c541c-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c541c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c541c-111">Requirements</span></span>  
 <span data-ttu-id="c541c-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c541c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c541c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c541c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c541c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c541c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c541c-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c541c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c541c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c541c-116">See Also</span></span>  
 [<span data-ttu-id="c541c-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c541c-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="c541c-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c541c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
