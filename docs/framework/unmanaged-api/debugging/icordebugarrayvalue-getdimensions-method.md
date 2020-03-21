---
title: ICorDebugArrayValue::GetDimensions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179016"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="9ec20-102">ICorDebugArrayValue::GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="9ec20-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="9ec20-103">Ruft die Anzahl der Elemente in jeder Dimension dieses Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="9ec20-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ec20-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ec20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ec20-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="9ec20-106">[in] Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="9ec20-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="9ec20-107">Dieser Wert ist auch `dims` die Größe des Arrays, da seine `ICorDebugArrayValue` Größe der Anzahl der Dimensionen des Objekts entspricht.</span><span class="sxs-lookup"><span data-stu-id="9ec20-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="9ec20-108">[out] Ein Array ganzer Zahlen, von denen jedes die Anzahl der `ICorDebugArrayValue` Elemente in einer Dimension in diesem Objekt angibt.</span><span class="sxs-lookup"><span data-stu-id="9ec20-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ec20-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9ec20-109">Requirements</span></span>  
 <span data-ttu-id="9ec20-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ec20-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ec20-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ec20-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ec20-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ec20-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ec20-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ec20-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
