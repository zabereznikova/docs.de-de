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
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122742"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="982ac-102">ICorDebugBreakpointEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="982ac-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="982ac-103">Ruft die angegebene Anzahl von icordebubreakpoint-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="982ac-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="982ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="982ac-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="982ac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="982ac-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="982ac-106">in Die Anzahl der `ICorDebugBreakpoint` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="982ac-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="982ac-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugBreakpoint` Objekt verweist, das einen Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="982ac-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="982ac-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugBreakpoint` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="982ac-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="982ac-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="982ac-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="982ac-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="982ac-110">Requirements</span></span>  
 <span data-ttu-id="982ac-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="982ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="982ac-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="982ac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="982ac-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="982ac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="982ac-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
