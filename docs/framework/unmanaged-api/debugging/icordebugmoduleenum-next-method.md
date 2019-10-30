---
title: ICorDebugModuleEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096930"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="e971c-102">ICorDebugModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e971c-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="e971c-103">Ruft die Anzahl der "ICorDebug Module"-Instanzen ab, die durch `celt` aus der-Enumeration angegeben werden, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="e971c-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e971c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e971c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e971c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e971c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e971c-106">in Die Anzahl der `ICorDebugModule` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e971c-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="e971c-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugModule` Objekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="e971c-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e971c-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugModule` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e971c-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="e971c-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="e971c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e971c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e971c-110">Requirements</span></span>  
 <span data-ttu-id="e971c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e971c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e971c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e971c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e971c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e971c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e971c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e971c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e971c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e971c-115">See also</span></span>
