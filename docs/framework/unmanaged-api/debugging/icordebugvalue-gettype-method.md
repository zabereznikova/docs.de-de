---
title: ICorDebugValue::GetType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d214da529aed40d33bdf18530560e9cd7b00f60a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="c09bd-102">ICorDebugValue::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="c09bd-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="c09bd-103">Ruft den primitiven Typ dieses Objekts "ICorDebugValue" ab.</span><span class="sxs-lookup"><span data-stu-id="c09bd-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c09bd-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c09bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c09bd-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="c09bd-106">[out] Ein Zeiger auf einen Wert von "CorElementType"-Enumeration, die den Werttyp angibt.</span><span class="sxs-lookup"><span data-stu-id="c09bd-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c09bd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c09bd-107">Remarks</span></span>  
 <span data-ttu-id="c09bd-108">Wenn das Objekt einen komplexen Typ für die Laufzeit ist, kann dieses Typs untersucht werden, über die entsprechenden Unterklasse von der `ICorDebugValue` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c09bd-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="c09bd-109">Z. B. "ICorDebugObjectValue", die erbt `ICorDebugValue`, stellt einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="c09bd-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="c09bd-110">Die `GetType` und [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) Methoden geben jeweils Informationen über den Typ eines Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="c09bd-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="c09bd-111">Sie werden sowohl von der Generika-bewusste abgelöst [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c09bd-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c09bd-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c09bd-112">Requirements</span></span>  
 <span data-ttu-id="c09bd-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c09bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c09bd-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c09bd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c09bd-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c09bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c09bd-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c09bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09bd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c09bd-117">See Also</span></span>  
 
