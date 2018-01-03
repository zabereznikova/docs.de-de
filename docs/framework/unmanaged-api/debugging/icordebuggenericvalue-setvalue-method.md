---
title: ICorDebugGenericValue::SetValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue.SetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11cb4ab6d32f3dbada25fe42f062fdc2c1fabd17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="82ff4-102">ICorDebugGenericValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="82ff4-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="82ff4-103">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="82ff4-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ff4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82ff4-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82ff4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82ff4-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="82ff4-106">[in] Ein Zeiger auf den Puffer, aus dem den Wert kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82ff4-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82ff4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82ff4-107">Remarks</span></span>  
 <span data-ttu-id="82ff4-108">Für Verweistypen ist der Wert der Verweis, nicht auf den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="82ff4-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82ff4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82ff4-109">Requirements</span></span>  
 <span data-ttu-id="82ff4-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82ff4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82ff4-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82ff4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82ff4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82ff4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82ff4-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82ff4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
