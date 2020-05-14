---
title: ICorDebugValueEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: db1721fed6414310556ceac493275e069a781ac8
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397144"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="cf062-102">ICorDebugValueEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="cf062-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="cf062-103">Ruft die angegebene Anzahl von "ICorDebug Value"-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="cf062-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf062-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf062-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf062-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf062-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cf062-106">in Die Anzahl der `ICorDebugValue` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="cf062-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="cf062-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugValue` Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="cf062-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cf062-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugValue` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="cf062-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="cf062-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="cf062-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf062-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf062-110">Requirements</span></span>  
 <span data-ttu-id="cf062-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf062-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf062-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf062-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf062-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf062-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf062-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf062-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf062-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf062-115">See also</span></span>
