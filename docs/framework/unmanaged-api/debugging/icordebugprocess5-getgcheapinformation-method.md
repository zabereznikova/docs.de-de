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
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670991"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="2ead6-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="2ead6-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>

<span data-ttu-id="2ead6-103">Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich dessen, ob er derzeit Aufzähl Bar ist.</span><span class="sxs-lookup"><span data-stu-id="2ead6-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ead6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ead6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ead6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ead6-105">Parameters</span></span>  

 `pHeapInfo`  
 <span data-ttu-id="2ead6-106">vorgenommen Ein Zeiger auf einen [COR_HEAPINFO](cor-heapinfo-structure.md) Wert, der allgemeine Informationen über den Garbage Collection Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2ead6-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ead6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ead6-107">Remarks</span></span>  

 <span data-ttu-id="2ead6-108">Die- `ICorDebugProcess5::GetGCHeapInformation` Methode muss aufgerufen werden, bevor der Heap oder einzelne Heap Regionen aufgelistet werden, um sicherzustellen, dass die Garbage Collection Strukturen im Prozess aktuell gültig sind.</span><span class="sxs-lookup"><span data-stu-id="2ead6-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="2ead6-109">Der Garbage Collection Heap kann nicht durchlaufen werden, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ead6-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="2ead6-110">Andernfalls kann die-Enumeration Garbage Collection Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="2ead6-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ead6-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ead6-111">Requirements</span></span>  

 <span data-ttu-id="2ead6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ead6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ead6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ead6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ead6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ead6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ead6-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ead6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ead6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ead6-116">See also</span></span>

- [<span data-ttu-id="2ead6-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ead6-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="2ead6-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ead6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
