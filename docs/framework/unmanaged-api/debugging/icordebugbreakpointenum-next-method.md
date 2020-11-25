---
title: ICorDebugBreakpointEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
ms.openlocfilehash: 14c89e808ea8e41bbee46a59a60bc1876f3800d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730187"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="43812-102">ICorDebugBreakpointEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="43812-102">ICorDebugBreakpointEnum::Next Method</span></span>

<span data-ttu-id="43812-103">Ruft die angegebene Anzahl von icordebubreakpoint-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="43812-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43812-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43812-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43812-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43812-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="43812-106">in Die Anzahl der `ICorDebugBreakpoint` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="43812-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="43812-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugBreakpoint` Objekt verweist, das einen Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="43812-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="43812-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugBreakpoint` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="43812-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="43812-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="43812-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43812-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43812-110">Requirements</span></span>  

 <span data-ttu-id="43812-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43812-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43812-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43812-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43812-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43812-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43812-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43812-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
