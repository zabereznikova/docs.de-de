---
title: ICorDebugValueEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a497488c06dd387f65182318c22f3189dfd7725
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="f0a19-102">ICorDebugValueEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f0a19-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="f0a19-103">Ruft die angegebene Anzahl von Instanzen von "ICorDebugValue" aus der Enumeration, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="f0a19-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0a19-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0a19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0a19-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f0a19-106">[in] Die Anzahl der `ICorDebugValue` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0a19-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f0a19-107">[out] Ein Array von Zeigern, die jeweils auf ein `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f0a19-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f0a19-108">[out] Zeiger auf die Anzahl der `ICorDebugValue` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0a19-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="f0a19-109">Dieser Wert kann null sein, wenn `celt` ist ein.</span><span class="sxs-lookup"><span data-stu-id="f0a19-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a19-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0a19-110">Requirements</span></span>  
 <span data-ttu-id="f0a19-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a19-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0a19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0a19-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0a19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0a19-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a19-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0a19-115">See Also</span></span>  
    
 
