---
title: ICorDebugValue::GetType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 06f403f0b653866428a41240f99833ec1180eb86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731071"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="27eea-102">ICorDebugValue::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="27eea-102">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="27eea-103">Ruft den primitiven Typ dieses ICorDebugValue-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="27eea-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27eea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27eea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27eea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27eea-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="27eea-106">vorgenommen Ein Zeiger auf einen Wert der "CorElementType"-Enumeration, der den Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="27eea-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27eea-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27eea-107">Remarks</span></span>  

 <span data-ttu-id="27eea-108">Wenn das-Objekt ein komplexer Lauf Zeittyp ist, kann dieser Typ durch die entsprechenden Unterklassen der- `ICorDebugValue` Schnittstelle überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="27eea-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="27eea-109">Beispielsweise stellt "ICorDebugObjectValue", der von erbt `ICorDebugValue` , einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="27eea-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="27eea-110">`GetType`Mit der-Methode und der [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) -Methode werden jeweils Informationen über den Typ eines Werts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27eea-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="27eea-111">Beide werden durch die Generics-Aware [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) -Methode abgelöst.</span><span class="sxs-lookup"><span data-stu-id="27eea-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27eea-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="27eea-112">Requirements</span></span>  

 <span data-ttu-id="27eea-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27eea-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27eea-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27eea-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27eea-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27eea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27eea-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27eea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27eea-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27eea-117">See also</span></span>
