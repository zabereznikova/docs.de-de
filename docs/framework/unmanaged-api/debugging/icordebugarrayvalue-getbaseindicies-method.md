---
title: ICorDebugArrayValue::GetBaseIndicies-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179035"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="14d94-102">ICorDebugArrayValue::GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="14d94-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="14d94-103">Ruft den Basisindex jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="14d94-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14d94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14d94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14d94-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="14d94-106">[in] Die Anzahl der `ICorDebugArrayValue` Dimensionen dieses Objekts.</span><span class="sxs-lookup"><span data-stu-id="14d94-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="14d94-107">Dieser Wert ist auch `indicies` die Größe des Arrays, da seine `ICorDebugArrayValue` Größe der Anzahl der Dimensionen des Objekts entspricht.</span><span class="sxs-lookup"><span data-stu-id="14d94-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="14d94-108">[out] Ein Array ganzer Zahlen, von denen jede der Basisindex (d. h. `ICorDebugArrayValue` der Startindex) einer Dimension dieses Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="14d94-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14d94-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14d94-109">Requirements</span></span>  
 <span data-ttu-id="14d94-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d94-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14d94-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14d94-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14d94-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14d94-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14d94-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14d94-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
