---
title: ICorDebugProcessEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcessEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 566d4a7eefee846f26abbc64f97e0063e847218b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="a27b3-102">ICorDebugProcessEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a27b3-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="a27b3-103">Ruft die angegebene Anzahl von Instanzen ICorDebugProcess aus der Enumeration, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="a27b3-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a27b3-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a27b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a27b3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a27b3-106">[in] Die Anzahl der `ICorDebugProcess` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a27b3-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processess`  
 <span data-ttu-id="a27b3-107">[out] Ein Array von Zeigern, die jeweils auf ein `ICorDebugProcess` Objekt, das einen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="a27b3-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a27b3-108">[out] Zeiger auf die Anzahl der `ICorDebugProcess` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a27b3-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="a27b3-109">Dieser Wert kann null sein, wenn `celt` ist ein.</span><span class="sxs-lookup"><span data-stu-id="a27b3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a27b3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a27b3-110">Requirements</span></span>  
 <span data-ttu-id="a27b3-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a27b3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a27b3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a27b3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a27b3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a27b3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a27b3-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a27b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
