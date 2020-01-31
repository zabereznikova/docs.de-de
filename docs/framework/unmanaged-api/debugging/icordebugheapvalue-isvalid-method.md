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
ms.openlocfilehash: 7685d1b6d5458a4405fc5a4abdb2f3134618f01c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794402"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="fa1f8-102">ICorDebugHeapValue::IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="fa1f8-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="fa1f8-103">Ruft einen Wert ab, der angibt, ob das von diesem ICorDebugHeapValue dargestellte Objekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="fa1f8-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa1f8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa1f8-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa1f8-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="fa1f8-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="fa1f8-107">vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob dieser Wert im Heap gültig ist.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa1f8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa1f8-108">Remarks</span></span>  
 <span data-ttu-id="fa1f8-109">Der Wert ist ungültig, wenn er vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="fa1f8-110">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-110">This method has been deprecated.</span></span> <span data-ttu-id="fa1f8-111">In den .NET Framework 2,0 sind alle Werte gültig, bis [icordbugcontroller:: Continue](icordebugcontroller-continue-method.md) aufgerufen wird. zu diesem Zeitpunkt werden die Werte für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="fa1f8-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa1f8-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa1f8-112">Requirements</span></span>  
 <span data-ttu-id="fa1f8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa1f8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa1f8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa1f8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa1f8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa1f8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa1f8-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa1f8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
