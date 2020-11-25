---
title: ICorDebugArrayValue::HasBaseIndicies-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: a9d1faf5a834cb5d9be19f995aaa3eee1202171b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727444"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="0d1b7-102">ICorDebugArrayValue::HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="0d1b7-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="0d1b7-103">Ruft einen Wert ab, der angibt, ob Dimensionen dieses Arrays einen Basis Index ungleich 0 (null) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d1b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d1b7-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d1b7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d1b7-105">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="0d1b7-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn mindestens eine Dimension dieses `ICorDebugArrayValue` Objekts einen Basis Index ungleich 0 (null) aufweist, andernfalls ist der boolesche Wert `false` .</span><span class="sxs-lookup"><span data-stu-id="0d1b7-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d1b7-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0d1b7-107">Requirements</span></span>  

 <span data-ttu-id="0d1b7-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d1b7-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d1b7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d1b7-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d1b7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d1b7-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d1b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
