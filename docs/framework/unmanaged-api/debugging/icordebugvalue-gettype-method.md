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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83265c4f6dffed76f1710378cf5293aac7020ef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119352"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="18ea6-102">ICorDebugValue::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="18ea6-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="18ea6-103">Ruft den primitiven Typ dieses Objekts "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="18ea6-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ea6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18ea6-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18ea6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="18ea6-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="18ea6-106">[out] Ein Zeiger auf einen Wert von "CorElementType"-Enumeration, die der Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="18ea6-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18ea6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18ea6-107">Remarks</span></span>  
 <span data-ttu-id="18ea6-108">Wenn das Objekt ein komplexer Typ für die Laufzeit ist, kann dieses Typs untersucht werden, über die entsprechenden Unterklassen von der `ICorDebugValue` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="18ea6-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="18ea6-109">Z. B. "ICorDebugObjectValue", die von erbt `ICorDebugValue`, stellt einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="18ea6-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="18ea6-110">Die `GetType` und [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) -Methode geben Informationen über den Typ eines Werts.</span><span class="sxs-lookup"><span data-stu-id="18ea6-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="18ea6-111">Sie werden beide ersetzt, durch die Generika-bewusste [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="18ea6-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18ea6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18ea6-112">Requirements</span></span>  
 <span data-ttu-id="18ea6-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18ea6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18ea6-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18ea6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18ea6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18ea6-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="18ea6-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="18ea6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18ea6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18ea6-117">See also</span></span>
