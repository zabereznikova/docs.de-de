---
title: ICorDebugArrayValue::HasBaseIndicies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.HasBaseIndicies
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 256429bfed350181aa13ee2c119eb5c9541ce231
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="a5741-102">ICorDebugArrayValue::HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="a5741-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="a5741-103">Ruft einen Wert, der angibt, ob alle Dimensionen dieses Arrays einen Basisindex ungleich Null aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a5741-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5741-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5741-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5741-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5741-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="a5741-106">[out] Ein Zeiger auf einen booleschen Wert, der `true` Wenn eine oder mehrere Dimensionen dieses `ICorDebugArrayValue` Objekt einen Basisindex ungleich Null aufweisen, andernfalls des booleschen Werts `false`.</span><span class="sxs-lookup"><span data-stu-id="a5741-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5741-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5741-107">Requirements</span></span>  
 <span data-ttu-id="a5741-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5741-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5741-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5741-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5741-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5741-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5741-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5741-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
