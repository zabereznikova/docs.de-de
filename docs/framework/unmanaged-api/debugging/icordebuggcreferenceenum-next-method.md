---
title: ICorDebugGCReferenceEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: e55c53b9610dcadee92ba9871bf52e3dacb5796b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726235"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="46665-102">ICorDebugGCReferenceEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="46665-102">ICorDebugGCReferenceEnum::Next Method</span></span>

<span data-ttu-id="46665-103">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46665-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46665-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46665-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46665-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="46665-105">Parameters</span></span>  

 <span data-ttu-id="46665-106">celt</span><span class="sxs-lookup"><span data-stu-id="46665-106">celt</span></span>  
 <span data-ttu-id="46665-107">in Die Anzahl der Stämme, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46665-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="46665-108">Basis</span><span class="sxs-lookup"><span data-stu-id="46665-108">roots</span></span>  
 <span data-ttu-id="46665-109">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekt verweist, das den Stamm eines Objekts darstellt, für das eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="46665-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="46665-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="46665-110">pceltFetched</span></span>  
 <span data-ttu-id="46665-111">vorgenommen Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](cor-gc-reference-structure.md) -Objekte, die tatsächlich in zurückgegeben werden `roots` .</span><span class="sxs-lookup"><span data-stu-id="46665-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="46665-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="46665-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46665-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46665-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46665-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="46665-114">Requirements</span></span>  

 <span data-ttu-id="46665-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46665-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46665-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46665-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46665-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46665-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46665-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46665-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46665-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46665-119">See also</span></span>

- [<span data-ttu-id="46665-120">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46665-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="46665-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="46665-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
