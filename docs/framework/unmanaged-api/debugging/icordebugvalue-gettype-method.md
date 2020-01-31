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
ms.openlocfilehash: 7def2bd2c0f3ab501fdb918a0e9a7ee154159b78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791155"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="c243b-102">ICorDebugValue::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="c243b-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="c243b-103">Ruft den primitiven Typ dieses ICorDebugValue-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="c243b-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c243b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c243b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c243b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c243b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="c243b-106">vorgenommen Ein Zeiger auf einen Wert der "CorElementType"-Enumeration, der den Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="c243b-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c243b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c243b-107">Remarks</span></span>  
 <span data-ttu-id="c243b-108">Wenn das Objekt ein komplexer Lauf Zeittyp ist, kann dieser Typ durch die entsprechenden Unterklassen der `ICorDebugValue`-Schnittstelle überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c243b-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="c243b-109">Beispielsweise stellt "ICorDebugObjectValue", der von `ICorDebugValue`erbt, einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="c243b-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="c243b-110">Die Methoden `GetType` und [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) geben Informationen über den Typ eines Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="c243b-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="c243b-111">Beide werden durch die Generics-Aware [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) -Methode abgelöst.</span><span class="sxs-lookup"><span data-stu-id="c243b-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c243b-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c243b-112">Requirements</span></span>  
 <span data-ttu-id="c243b-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c243b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c243b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c243b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c243b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c243b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c243b-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c243b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c243b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c243b-117">See also</span></span>
