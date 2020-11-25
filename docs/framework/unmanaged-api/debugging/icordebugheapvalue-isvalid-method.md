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
ms.openlocfilehash: d9150d15ac183b65b87448424f265693ed7b7ab7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726573"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="0bd41-102">ICorDebugHeapValue::IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="0bd41-102">ICorDebugHeapValue::IsValid Method</span></span>

<span data-ttu-id="0bd41-103">Ruft einen Wert ab, der angibt, ob das von diesem ICorDebugHeapValue dargestellte Objekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="0bd41-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="0bd41-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="0bd41-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd41-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bd41-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bd41-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bd41-106">Parameters</span></span>  

 `pbValid`  
 <span data-ttu-id="0bd41-107">vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob dieser Wert im Heap gültig ist.</span><span class="sxs-lookup"><span data-stu-id="0bd41-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bd41-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bd41-108">Remarks</span></span>  

 <span data-ttu-id="0bd41-109">Der Wert ist ungültig, wenn er vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0bd41-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="0bd41-110">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="0bd41-110">This method has been deprecated.</span></span> <span data-ttu-id="0bd41-111">In den .NET Framework 2,0 sind alle Werte gültig, bis [icordbugcontroller:: Continue](icordebugcontroller-continue-method.md) aufgerufen wird. zu diesem Zeitpunkt werden die Werte für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="0bd41-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd41-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0bd41-112">Requirements</span></span>  

 <span data-ttu-id="0bd41-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bd41-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bd41-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bd41-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bd41-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bd41-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bd41-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bd41-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
