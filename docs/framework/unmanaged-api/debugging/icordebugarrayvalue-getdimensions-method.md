---
title: ICorDebugArrayValue::GetDimensions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1769969d411d66417d2b2df7ddc9f810bd7f48ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="21503-102">ICorDebugArrayValue::GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="21503-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="21503-103">Ruft die Anzahl der Elemente in jeder Dimension dieses Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="21503-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21503-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21503-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21503-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21503-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="21503-106">[in] Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="21503-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="21503-107">Dieser Wert ist auch die Größe der `dims` Arrays, da seine Größe gleich der Anzahl der Dimensionen des ist die `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="21503-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="21503-108">[out] Ein Array von Ganzzahlen, von denen jede die Anzahl der Elemente in einer Dimension in dieser gibt `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="21503-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21503-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21503-109">Requirements</span></span>  
 <span data-ttu-id="21503-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21503-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21503-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21503-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21503-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21503-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21503-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21503-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
