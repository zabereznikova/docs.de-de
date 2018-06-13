---
title: ICorDebugHeapSegmentEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b63646b54b73c30abf0ddb9a06a982f1364ef87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417023"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="a9a57-102">ICorDebugHeapSegmentEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a9a57-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="a9a57-103">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen über die Speicherbereiche des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9a57-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9a57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9a57-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9a57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9a57-105">Parameters</span></span>  
 <span data-ttu-id="a9a57-106">celt</span><span class="sxs-lookup"><span data-stu-id="a9a57-106">celt</span></span>  
 <span data-ttu-id="a9a57-107">[in] Die Anzahl der Segmente abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a9a57-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="a9a57-108">Segmente</span><span class="sxs-lookup"><span data-stu-id="a9a57-108">segments</span></span>  
 <span data-ttu-id="a9a57-109">[out] Ein Array von Zeigern, die jeweils auf eine [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekt, das Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a9a57-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="a9a57-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="a9a57-110">pceltFetched</span></span>  
 <span data-ttu-id="a9a57-111">[out] Ein Zeiger auf die Anzahl der [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) tatsächlich zurückgegebenen Objekte `segments`.</span><span class="sxs-lookup"><span data-stu-id="a9a57-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="a9a57-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="a9a57-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9a57-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9a57-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9a57-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9a57-114">Requirements</span></span>  
 <span data-ttu-id="a9a57-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a57-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a57-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9a57-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9a57-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9a57-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9a57-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a57-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a57-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a57-119">See Also</span></span>  
 [<span data-ttu-id="a9a57-120">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a57-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 [<span data-ttu-id="a9a57-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9a57-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
