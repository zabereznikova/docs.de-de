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
ms.openlocfilehash: 89ce4eafa46be3e9ba7cdb06884034a521e43bca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777540"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="29c99-102">ICorDebugHeapSegmentEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="29c99-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="29c99-103">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen über die Speicherbereiche des verwalteten Heaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="29c99-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29c99-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29c99-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="29c99-105">Parameters</span></span>  
 <span data-ttu-id="29c99-106">celt</span><span class="sxs-lookup"><span data-stu-id="29c99-106">celt</span></span>  
 <span data-ttu-id="29c99-107">in Die Anzahl der abzurufenden Segmente.</span><span class="sxs-lookup"><span data-stu-id="29c99-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="29c99-108">Segmente</span><span class="sxs-lookup"><span data-stu-id="29c99-108">segments</span></span>  
 <span data-ttu-id="29c99-109">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekt verweist, das Informationen zu einem Speicherbereich im verwalteten Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="29c99-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="29c99-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="29c99-110">pceltFetched</span></span>  
 <span data-ttu-id="29c99-111">vorgenommen Ein Zeiger auf die Anzahl der [COR_HEAPOBJECT](cor-heapobject-structure.md) -Objekte, die tatsächlich in `segments`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="29c99-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="29c99-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="29c99-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29c99-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29c99-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c99-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29c99-114">Requirements</span></span>  
 <span data-ttu-id="29c99-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c99-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c99-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c99-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c99-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c99-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c99-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c99-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c99-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29c99-119">See also</span></span>

- [<span data-ttu-id="29c99-120">ICorDebugHeapSegmentEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29c99-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="29c99-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="29c99-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
