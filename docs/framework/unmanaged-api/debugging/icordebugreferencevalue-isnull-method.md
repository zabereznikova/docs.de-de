---
title: ICorDebugReferenceValue::IsNull-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: bcd4c8ba4b81821ae7dd9deaf0f76a76d335aff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728393"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="b53eb-102">ICorDebugReferenceValue::IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="b53eb-102">ICorDebugReferenceValue::IsNull Method</span></span>

<span data-ttu-id="b53eb-103">Ruft einen Wert ab, der angibt, ob dieser ICorDebugReferenceValue ein NULL-Wert ist. in diesem Fall verweist der `ICorDebugReferenceValue` nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="b53eb-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b53eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b53eb-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b53eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b53eb-105">Parameters</span></span>  

 `pbNull`  
 <span data-ttu-id="b53eb-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn dieses `ICorDebugReferenceValue` Objekt NULL ist, andernfalls `pbNull` ist `false` .</span><span class="sxs-lookup"><span data-stu-id="b53eb-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b53eb-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b53eb-107">Requirements</span></span>  

 <span data-ttu-id="b53eb-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b53eb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53eb-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b53eb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b53eb-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b53eb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b53eb-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b53eb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
