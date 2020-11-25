---
title: ICorDebugTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 78ea76033b0b83c84446e16fb330bd3ba34c6e21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725702"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="9d9fd-102">ICorDebugTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9d9fd-102">ICorDebugTypeEnum::Next Method</span></span>

<span data-ttu-id="9d9fd-103">Ruft die Anzahl der "ICorDebugType"-Instanzen ab `celt` , die von der-Enumeration angegeben werden, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="9d9fd-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d9fd-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d9fd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d9fd-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9d9fd-106">in Die Anzahl der `ICorDebugType` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9d9fd-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9d9fd-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugType` Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="9d9fd-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9d9fd-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugType` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9d9fd-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="9d9fd-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="9d9fd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d9fd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9d9fd-110">Requirements</span></span>  

 <span data-ttu-id="9d9fd-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d9fd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d9fd-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d9fd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d9fd-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d9fd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d9fd-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d9fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9fd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d9fd-115">See also</span></span>
