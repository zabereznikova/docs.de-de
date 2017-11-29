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
ms.openlocfilehash: da423914d8af20c0f942d53ed6ac9f34ace01ca9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="3ecb2-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="3ecb2-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="3ecb2-103">Allgemeine Informationen zum Garbage Collection-Heap, z. B. ob er derzeit aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="3ecb2-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecb2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ecb2-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ecb2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ecb2-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="3ecb2-106">[out] Ein Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Werte, die allgemeine Informationen zum Garbage Collection-Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3ecb2-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ecb2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ecb2-107">Remarks</span></span>  
 <span data-ttu-id="3ecb2-108">Die `ICorDebugProcess5::GetGCHeapInformation` Methode muss aufgerufen werden, bevor beim Aufzählen der Heap oder einzelne Heap Regionen, um sicherzustellen, dass die Garbagecollection-im Prozess Strukturen derzeit gültig sind.</span><span class="sxs-lookup"><span data-stu-id="3ecb2-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="3ecb2-109">Garbage Collection-Heap kann nicht durchlaufen werden soll, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ecb2-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="3ecb2-110">Andernfalls kann die Enumeration Garbage Collection-Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="3ecb2-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ecb2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ecb2-111">Requirements</span></span>  
 <span data-ttu-id="3ecb2-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ecb2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ecb2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ecb2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ecb2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ecb2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ecb2-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ecb2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecb2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ecb2-116">See Also</span></span>  
 [<span data-ttu-id="3ecb2-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ecb2-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="3ecb2-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ecb2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
