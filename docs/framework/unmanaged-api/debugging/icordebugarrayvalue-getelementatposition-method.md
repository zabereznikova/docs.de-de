---
title: ICorDebugArrayValue::GetElementAtPosition-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetElementAtPosition
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c26a55815e57126895902275148940c5271c235b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="4639c-102">ICorDebugArrayValue::GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="4639c-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="4639c-103">Ruft das Element an der angegebenen Position, behandelt das Array als ein nullbasiertes, eindimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="4639c-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4639c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4639c-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4639c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4639c-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="4639c-106">[in] Die Position des Elements, das abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4639c-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4639c-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="4639c-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4639c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4639c-108">Remarks</span></span>  
 <span data-ttu-id="4639c-109">Das Layout eines mehrdimensionalen Arrays folgt den C++-Stil Layout für das Array.</span><span class="sxs-lookup"><span data-stu-id="4639c-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4639c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4639c-110">Requirements</span></span>  
 <span data-ttu-id="4639c-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4639c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4639c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4639c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4639c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4639c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4639c-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4639c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
