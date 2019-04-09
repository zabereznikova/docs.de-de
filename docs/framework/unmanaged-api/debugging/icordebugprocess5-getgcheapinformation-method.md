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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140542"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="b03b0-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="b03b0-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="b03b0-103">Enthält allgemeine Informationen zur Garbage Collection-Heap, z. B., ob sie derzeit aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="b03b0-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b03b0-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b03b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b03b0-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="b03b0-106">[out] Ein Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Wert, der allgemeine Informationen zur Garbage Collection-Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b03b0-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b03b0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b03b0-107">Remarks</span></span>  
 <span data-ttu-id="b03b0-108">Die `ICorDebugProcess5::GetGCHeapInformation` -Methode muss aufgerufen werden, vor der Enumeration des Heaps oder einzelne Heap-Regionen, um sicherzustellen, dass die Garbagecollection im Prozess Strukturen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="b03b0-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="b03b0-109">Garbage Collection-Heap kann nicht durchlaufen werden soll, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b03b0-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="b03b0-110">Andernfalls kann die Enumeration Garbage Collection-Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="b03b0-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03b0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b03b0-111">Requirements</span></span>  
 <span data-ttu-id="b03b0-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b03b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03b0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b03b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b03b0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03b0-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b03b0-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b03b0-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b03b0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b03b0-116">See also</span></span>

- [<span data-ttu-id="b03b0-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b03b0-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="b03b0-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b03b0-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
