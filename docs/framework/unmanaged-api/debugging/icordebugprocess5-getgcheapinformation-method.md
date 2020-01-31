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
ms.openlocfilehash: 703f159c5bc6b73dcd0e770bdeb61f676aae034c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792377"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="b1d88-102">ICorDebugProcess5::GetGCHeapInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="b1d88-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="b1d88-103">Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich dessen, ob er derzeit Aufzähl Bar ist.</span><span class="sxs-lookup"><span data-stu-id="b1d88-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1d88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1d88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1d88-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b1d88-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="b1d88-106">vorgenommen Ein Zeiger auf einen [COR_HEAPINFO](cor-heapinfo-structure.md) Wert, der allgemeine Informationen über den Garbage Collection Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b1d88-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1d88-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1d88-107">Remarks</span></span>  
 <span data-ttu-id="b1d88-108">Die `ICorDebugProcess5::GetGCHeapInformation`-Methode muss aufgerufen werden, bevor der Heap oder einzelne Heap Regionen aufgelistet werden, um sicherzustellen, dass die Garbage Collection Strukturen im Prozess aktuell gültig sind.</span><span class="sxs-lookup"><span data-stu-id="b1d88-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="b1d88-109">Der Garbage Collection Heap kann nicht durchlaufen werden, während eine Sammlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1d88-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="b1d88-110">Andernfalls kann die-Enumeration Garbage Collection Strukturen erfassen, die ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="b1d88-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1d88-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1d88-111">Requirements</span></span>  
 <span data-ttu-id="b1d88-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d88-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1d88-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1d88-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1d88-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1d88-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d88-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d88-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1d88-116">See also</span></span>

- [<span data-ttu-id="b1d88-117">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1d88-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="b1d88-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1d88-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
