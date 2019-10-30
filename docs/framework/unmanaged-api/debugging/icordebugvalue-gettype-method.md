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
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137076"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="9535c-102">ICorDebugValue::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="9535c-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="9535c-103">Ruft den primitiven Typ dieses ICorDebugValue-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="9535c-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9535c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9535c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9535c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9535c-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="9535c-106">vorgenommen Ein Zeiger auf einen Wert der "CorElementType"-Enumeration, der den Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="9535c-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9535c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9535c-107">Remarks</span></span>  
 <span data-ttu-id="9535c-108">Wenn das Objekt ein komplexer Lauf Zeittyp ist, kann dieser Typ durch die entsprechenden Unterklassen der `ICorDebugValue`-Schnittstelle überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="9535c-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="9535c-109">Beispielsweise stellt "ICorDebugObjectValue", der von `ICorDebugValue`erbt, einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="9535c-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="9535c-110">Die Methoden `GetType` und [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) geben Informationen über den Typ eines Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="9535c-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="9535c-111">Beide werden durch die Generics-Aware [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) -Methode abgelöst.</span><span class="sxs-lookup"><span data-stu-id="9535c-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9535c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9535c-112">Requirements</span></span>  
 <span data-ttu-id="9535c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9535c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9535c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9535c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9535c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9535c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9535c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9535c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9535c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9535c-117">See also</span></span>
