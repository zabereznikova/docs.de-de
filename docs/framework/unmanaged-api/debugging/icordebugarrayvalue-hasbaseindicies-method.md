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
ms.openlocfilehash: e6e8eb91bbc41faf0dcea010da9aa54995058653
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894977"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="5da7c-102">ICorDebugArrayValue::HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="5da7c-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="5da7c-103">Ruft einen Wert ab, der angibt, ob Dimensionen dieses Arrays einen Basis Index ungleich 0 (null) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5da7c-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5da7c-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5da7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5da7c-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="5da7c-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der `true` ist, wenn mindestens eine Dimension dieses `ICorDebugArrayValue` Objekts einen Basis Index ungleich 0 (null) aufweist. Andernfalls ist `false`der boolesche Wert.</span><span class="sxs-lookup"><span data-stu-id="5da7c-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da7c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5da7c-107">Requirements</span></span>  
 <span data-ttu-id="5da7c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5da7c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da7c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5da7c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5da7c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da7c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da7c-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
