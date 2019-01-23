---
title: ICorDebugCodeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45caad20ef7d2dbe35e0381fb8cd697fc526398f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529803"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="480f4-102">ICorDebugCodeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="480f4-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="480f4-103">Ruft die angegebene Anzahl von Instanzen von "ICorDebugCode" aus der Enumeration ab, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="480f4-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="480f4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="480f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="480f4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="480f4-106">[in] Die Anzahl der `ICorDebugCode` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="480f4-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="480f4-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugCode` Objekt.</span><span class="sxs-lookup"><span data-stu-id="480f4-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="480f4-108">[out] Ein Zeiger auf die Anzahl der `ICorDebugCode` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="480f4-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="480f4-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="480f4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="480f4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="480f4-110">Requirements</span></span>  
 <span data-ttu-id="480f4-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="480f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="480f4-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="480f4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="480f4-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="480f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="480f4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="480f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480f4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="480f4-115">See also</span></span>


