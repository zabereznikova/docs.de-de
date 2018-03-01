---
title: ICorDebugEval::CreateValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64d55a951795cc5efc1bfc624dbe07575be153aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="e01d2-102">ICorDebugEval::CreateValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e01d2-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="e01d2-103">Erstellt einen Wert des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null.</span><span class="sxs-lookup"><span data-stu-id="e01d2-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="e01d2-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="e01d2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e01d2-105">Verwendung [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="e01d2-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e01d2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e01d2-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e01d2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e01d2-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="e01d2-108">[in] Der Wert der [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) -Enumeration, der den Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="e01d2-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="e01d2-109">[in] Zeiger auf eine [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) -Objekt, das die Klasse der der Wert gibt an, wenn der Typ kein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="e01d2-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e01d2-110">[out] Zeiger auf die Adresse eines Objekts "ICorDebugValue", das den Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e01d2-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e01d2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e01d2-111">Remarks</span></span>  
 <span data-ttu-id="e01d2-112">`CreateValue`erstellt ein `ICorDebugValue` Objekt des angegebenen Typs für der einzige Zweck der Verwendung in einer funktionsauswertung.</span><span class="sxs-lookup"><span data-stu-id="e01d2-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="e01d2-113">Dieser Wertobjekt kann verwendet werden, Benutzerkonstanten als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="e01d2-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="e01d2-114">Wenn der Typ des Werts ein primitiver Typ ist, ist der Anfangswert 0 (null) oder null.</span><span class="sxs-lookup"><span data-stu-id="e01d2-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="e01d2-115">Verwendung [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) zum Festlegen des Werts eines primitiven Typs.</span><span class="sxs-lookup"><span data-stu-id="e01d2-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="e01d2-116">Wenn der Wert der `elementType` ELEMENT_TYPE_CLASS lautet, erhalten Sie eine "ICorDebugReferenceValue" (im zurückgegebenen `ppValue`), die null-Objektverweis darstellt.</span><span class="sxs-lookup"><span data-stu-id="e01d2-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="e01d2-117">Dieses Objekt können Sie null für eine funktionsauswertung übergeben, die Objektverweisparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="e01d2-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="e01d2-118">Kann nicht festgelegt werden die `ICorDebugValue` anderer Wert; er bleibt immer null.</span><span class="sxs-lookup"><span data-stu-id="e01d2-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e01d2-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e01d2-119">Requirements</span></span>  
 <span data-ttu-id="e01d2-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e01d2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e01d2-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e01d2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e01d2-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e01d2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e01d2-123">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e01d2-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e01d2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e01d2-124">See Also</span></span>  
    
 [<span data-ttu-id="e01d2-125">CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="e01d2-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 <span data-ttu-id="e01d2-126">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="e01d2-126">ICorDebugValue</span></span>
