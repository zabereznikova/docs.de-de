---
title: ICorDebugHeapValue::IsValid-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700224"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="82702-102">ICorDebugHeapValue::IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="82702-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="82702-103">Ruft einen Wert, der angibt, ob das durch diesen ICorDebugHeapValue dargestellte Objekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="82702-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="82702-104">Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="82702-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82702-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="82702-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82702-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="82702-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="82702-107">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob dieser Wert auf dem Heap gültig ist.</span><span class="sxs-lookup"><span data-stu-id="82702-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82702-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82702-108">Remarks</span></span>  
 <span data-ttu-id="82702-109">Der Wert ist ungültig, wenn es vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="82702-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="82702-110">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="82702-110">This method has been deprecated.</span></span> <span data-ttu-id="82702-111">In .NET Framework 2.0, alle Werte sind gültig bis [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird, an der Zeit werden die Werte ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="82702-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82702-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82702-112">Requirements</span></span>  
 <span data-ttu-id="82702-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82702-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82702-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82702-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82702-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82702-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82702-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82702-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
