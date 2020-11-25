---
title: ICorDebugProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 6aee88452819a4aabe2a29971ce86079ef7f0008
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732501"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="556e7-102">ICorDebugProcessEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="556e7-102">ICorDebugProcessEnum::Next Method</span></span>

<span data-ttu-id="556e7-103">Ruft die angegebene Anzahl von ICorDebugProcess-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="556e7-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="556e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="556e7-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="556e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="556e7-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="556e7-106">in Die Anzahl der `ICorDebugProcess` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="556e7-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="556e7-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugProcess` Objekt verweist, das einen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="556e7-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="556e7-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugProcess` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="556e7-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="556e7-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="556e7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="556e7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="556e7-110">Requirements</span></span>  

 <span data-ttu-id="556e7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="556e7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="556e7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="556e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="556e7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="556e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="556e7-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="556e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
