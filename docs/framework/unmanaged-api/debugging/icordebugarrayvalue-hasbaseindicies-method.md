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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49f5ed8b24d81ba8f32a9fe0ad7488693718bde9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645668"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="dfb39-102">ICorDebugArrayValue::HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="dfb39-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="dfb39-103">Ruft einen Wert, der angibt, ob alle Dimensionen dieses Arrays einen Basisindex ungleich Null aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dfb39-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfb39-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfb39-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="dfb39-106">[out] Ein Zeiger auf einen booleschen Wert, der `true` Wenn eine oder mehrere Dimensionen dieses `ICorDebugArrayValue` Objekt einen Basisindex ungleich Null aufweisen, andernfalls der boolesche Wert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="dfb39-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb39-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfb39-107">Requirements</span></span>  
 <span data-ttu-id="dfb39-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb39-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb39-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfb39-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfb39-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb39-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb39-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb39-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
