---
title: ICorDebugEval::CreateValue-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976251"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="6acf2-102">ICorDebugEval::CreateValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6acf2-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="6acf2-103">Erstellt einen Wert vom angegebenen Typ mit einem Anfangswert von 0 (null) oder NULL.</span><span class="sxs-lookup"><span data-stu-id="6acf2-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="6acf2-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6acf2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6acf2-105">Verwenden Sie stattdessen [ICorDebugEval2:: kreatevaluefortype](icordebugeval2-createvaluefortype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6acf2-105">Use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acf2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6acf2-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6acf2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6acf2-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="6acf2-108">in Ein Wert der [CorElementType](../metadata/corelementtype-enumeration.md) -Enumeration, der den Typ des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="6acf2-108">[in] A value of the [CorElementType](../metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="6acf2-109">in Ein Zeiger auf ein [ICorDebugClass](icordebugclass-interface.md) -Objekt, das die Klasse des Werts angibt, wenn der Typ kein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="6acf2-109">[in] Pointer to an [ICorDebugClass](icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6acf2-110">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="6acf2-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6acf2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6acf2-111">Remarks</span></span>  
 <span data-ttu-id="6acf2-112">`CreateValue`erstellt ein `ICorDebugValue` Objekt des angegebenen Typs für den alleinigen Zweck der Verwendung in einer Funktions Auswertung.</span><span class="sxs-lookup"><span data-stu-id="6acf2-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="6acf2-113">Dieses Wertobjekt kann verwendet werden, um Benutzer Konstanten als Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="6acf2-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="6acf2-114">Wenn der Typ des Werts ein primitiver Typ ist, ist der anfängliche Wert 0 (null) oder NULL.</span><span class="sxs-lookup"><span data-stu-id="6acf2-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="6acf2-115">Verwenden Sie [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) , um den Wert eines primitiven Typs festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6acf2-115">Use [ICorDebugGenericValue::SetValue](icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="6acf2-116">Wenn der Wert von `elementType` ELEMENT_TYPE_CLASS ist, erhalten Sie einen "ICorDebugReferenceValue" (zurückgegeben `ppValue`in), der den NULL-Objekt Verweis darstellt.</span><span class="sxs-lookup"><span data-stu-id="6acf2-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="6acf2-117">Sie können dieses Objekt verwenden, um NULL an eine Funktions Auswertung zu übergeben, die über Objekt Verweis Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="6acf2-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="6acf2-118">Sie können den `ICorDebugValue` nicht auf "nichts" festlegen. Sie bleibt immer NULL.</span><span class="sxs-lookup"><span data-stu-id="6acf2-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acf2-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6acf2-119">Requirements</span></span>  
 <span data-ttu-id="6acf2-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acf2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acf2-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6acf2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6acf2-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6acf2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6acf2-123">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="6acf2-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acf2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6acf2-124">See also</span></span>

- [<span data-ttu-id="6acf2-125">CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="6acf2-125">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="6acf2-126">ICorDebugEval-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6acf2-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
