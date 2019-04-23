---
title: ICorDebugProcess5::GetGCHeapInformation-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50b682a7b3a4aadf7559120745265ef266cf2870
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140542"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="46524-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="46524-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="46524-103">Enthält allgemeine Informationen zur Garbage Collection-Heap, z. B., ob sie derzeit aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="46524-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46524-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46524-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46524-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="46524-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="46524-106">[out] Ein Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Wert, der allgemeine Informationen zur Garbage Collection-Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="46524-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46524-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46524-107">Remarks</span></span>  
 <span data-ttu-id="46524-108">Die `ICorDebugProcess5::GetGCHeapInformation` -Methode muss aufgerufen werden, vor der Enumeration des Heaps oder einzelne Heap-Regionen, um sicherzustellen, dass die Garbagecollection im Prozess Strukturen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="46524-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="46524-109">Garbage Collection-Heap kann nicht durchlaufen werden soll, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46524-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="46524-110">Andernfalls kann die Enumeration Garbage Collection-Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="46524-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46524-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46524-111">Requirements</span></span>  
 <span data-ttu-id="46524-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46524-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46524-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46524-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46524-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46524-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46524-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46524-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46524-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46524-116">See also</span></span>

- [<span data-ttu-id="46524-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46524-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="46524-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="46524-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
