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
ms.openlocfilehash: fa2be894af6e44d09c25a736f45acba56052f9fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895038"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="387b5-102">ICorDebugArrayValue::GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="387b5-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="387b5-103">Ruft die Anzahl der Elemente in jeder Dimension dieses Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="387b5-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="387b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="387b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="387b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="387b5-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="387b5-106">in Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="387b5-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="387b5-107">Dieser Wert ist auch die Größe des `dims` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="387b5-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="387b5-108">vorgenommen Ein Array von ganzen Zahlen, von denen jede die Anzahl der Elemente in einer Dimension in diesem `ICorDebugArrayValue` -Objekt angibt.</span><span class="sxs-lookup"><span data-stu-id="387b5-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="387b5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="387b5-109">Requirements</span></span>  
 <span data-ttu-id="387b5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="387b5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="387b5-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="387b5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="387b5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="387b5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="387b5-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="387b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
