---
title: ICorDebugHeapValue::IsValid-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue.IsValid
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df7105c94a6f88c9c196f1d9d6be6f4a62f7c258
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="f3acc-102">ICorDebugHeapValue::IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="f3acc-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="f3acc-103">Ruft einen Wert, der angibt, ob das durch diese ICorDebugHeapValue dargestellte Objekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f3acc-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="f3acc-104">Diese Methode ist in .NET Framework, Version 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="f3acc-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3acc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3acc-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3acc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3acc-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="f3acc-107">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob dieser Wert auf dem Heap gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f3acc-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3acc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3acc-108">Remarks</span></span>  
 <span data-ttu-id="f3acc-109">Der Wert ist ungültig, wenn er vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f3acc-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="f3acc-110">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f3acc-110">This method has been deprecated.</span></span> <span data-ttu-id="f3acc-111">In .NET Framework 2.0 können alle Werte sind gültig, bis [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird, an welche die Werte ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="f3acc-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3acc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3acc-112">Requirements</span></span>  
 <span data-ttu-id="f3acc-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3acc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3acc-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3acc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3acc-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3acc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3acc-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3acc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
