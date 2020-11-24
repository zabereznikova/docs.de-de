---
title: ICorDebugThreadEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 226b386c7a38c9a0b28b3bcc0420d14f6f4f4e7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678414"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="8b6d3-102">ICorDebugThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8b6d3-102">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="8b6d3-103">Ruft die Anzahl der angegebenen ICorDebugThread-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="8b6d3-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b6d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b6d3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b6d3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b6d3-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="8b6d3-106">in Die Anzahl der `ICorDebugThread` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="8b6d3-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="8b6d3-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugThread` Objekt verweist, das einen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b6d3-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8b6d3-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugThread` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="8b6d3-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="8b6d3-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="8b6d3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b6d3-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b6d3-110">Requirements</span></span>  

 <span data-ttu-id="8b6d3-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b6d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b6d3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b6d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b6d3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b6d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b6d3-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b6d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
