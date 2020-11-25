---
title: ICorDebugHeapEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 320b3ca55a60ec7751c88a246ab6ee90b6b6c4cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724350"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="8b537-102">ICorDebugHeapEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8b537-102">ICorDebugHeapEnum::Next Method</span></span>

<span data-ttu-id="8b537-103">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen zu Objekten im verwalteten Heap enthalten.</span><span class="sxs-lookup"><span data-stu-id="8b537-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b537-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b537-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b537-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b537-105">Parameters</span></span>  

 <span data-ttu-id="8b537-106">celt</span><span class="sxs-lookup"><span data-stu-id="8b537-106">celt</span></span>  
 <span data-ttu-id="8b537-107">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="8b537-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="8b537-108">Objekte</span><span class="sxs-lookup"><span data-stu-id="8b537-108">objects</span></span>  
 <span data-ttu-id="8b537-109">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekt verweist, das Informationen zu einem Objekt auf dem verwalteten Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8b537-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="8b537-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="8b537-110">pceltFetched</span></span>  
 <span data-ttu-id="8b537-111">vorgenommen Ein Zeiger auf die Anzahl der [COR_HEAPOBJECT](cor-heapobject-structure.md) -Objekte, die tatsächlich in zurückgegeben werden `objects` .</span><span class="sxs-lookup"><span data-stu-id="8b537-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="8b537-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="8b537-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b537-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b537-113">Remarks</span></span>  

 <span data-ttu-id="8b537-114">Das `COR_HEAPOBJECT.type`-Feld ist der Bezeichner einer geschachtelten COM-Schnittstelle mit Referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="8b537-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="8b537-115">Diese Referenz muss von dem Aufrufer von `ICorDebugHeapEnum::Next` freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8b537-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b537-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b537-116">Requirements</span></span>  

 <span data-ttu-id="8b537-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b537-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b537-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b537-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b537-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b537-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b537-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b537-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b537-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b537-121">See also</span></span>

- [<span data-ttu-id="8b537-122">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b537-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="8b537-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8b537-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
