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
ms.openlocfilehash: fc205e347fc39fd486d9b8a3fb256a5d29a980a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110065"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="e9d66-102">ICorDebugTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e9d66-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="e9d66-103">Ruft die Anzahl der "ICorDebugType"-Instanzen ab, die `celt` von der-Enumeration angegeben werden, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="e9d66-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d66-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d66-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9d66-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e9d66-106">in Die Anzahl der `ICorDebugType` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e9d66-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="e9d66-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugType` Objekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="e9d66-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e9d66-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugType` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e9d66-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="e9d66-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="e9d66-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d66-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9d66-110">Requirements</span></span>  
 <span data-ttu-id="e9d66-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d66-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d66-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9d66-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9d66-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9d66-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9d66-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d66-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d66-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d66-115">See also</span></span>
