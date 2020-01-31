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
ms.openlocfilehash: 3a8e967a3ecc452ebda08872d8bcd9e9d08c766f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777689"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="fa1c0-102">ICorDebugGCReferenceEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="fa1c0-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="fa1c0-103">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa1c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa1c0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa1c0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fa1c0-105">Parameters</span></span>  
 <span data-ttu-id="fa1c0-106">celt</span><span class="sxs-lookup"><span data-stu-id="fa1c0-106">celt</span></span>  
 <span data-ttu-id="fa1c0-107">in Die Anzahl der Stämme, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="fa1c0-108">Basis</span><span class="sxs-lookup"><span data-stu-id="fa1c0-108">roots</span></span>  
 <span data-ttu-id="fa1c0-109">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekt verweist, das den Stamm eines Objekts darstellt, für das eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="fa1c0-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="fa1c0-110">pceltFetched</span></span>  
 <span data-ttu-id="fa1c0-111">vorgenommen Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](cor-gc-reference-structure.md) -Objekte, die tatsächlich in `roots`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="fa1c0-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa1c0-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa1c0-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa1c0-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa1c0-114">Requirements</span></span>  
 <span data-ttu-id="fa1c0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa1c0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa1c0-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa1c0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa1c0-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa1c0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa1c0-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa1c0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa1c0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa1c0-119">See also</span></span>

- [<span data-ttu-id="fa1c0-120">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa1c0-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="fa1c0-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa1c0-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
