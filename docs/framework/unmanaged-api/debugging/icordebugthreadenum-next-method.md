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
ms.openlocfilehash: 0c455706b0d644d2444e9fbdf49c5a5d4f5295a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122388"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="d1e75-102">ICorDebugThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="d1e75-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="d1e75-103">Ruft die Anzahl der angegebenen ICorDebugThread-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="d1e75-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1e75-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1e75-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d1e75-106">in Die Anzahl der `ICorDebugThread` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d1e75-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="d1e75-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugThread` Objekt verweist, das einen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1e75-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d1e75-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugThread` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="d1e75-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="d1e75-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="d1e75-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e75-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1e75-110">Requirements</span></span>  
 <span data-ttu-id="d1e75-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e75-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e75-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1e75-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1e75-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1e75-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1e75-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
