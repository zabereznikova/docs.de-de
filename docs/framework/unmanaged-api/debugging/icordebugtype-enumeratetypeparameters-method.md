---
title: ICorDebugType::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: 3717497ab6e72f0ce67f688813ee7264206e8c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727951"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="f2ab2-102">ICorDebugType::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ab2-102">ICorDebugType::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="f2ab2-103">Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die die <xref:System.Type> Parameter der Klasse enthält, auf die von diesem ICorDebugType verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ab2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2ab2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ab2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2ab2-105">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="f2ab2-106">vorgenommen Ein Zeiger auf die Adresse eines- `ICorDebugTypeEnum` Parameters, der die Parameter des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ab2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2ab2-107">Remarks</span></span>  

 <span data-ttu-id="f2ab2-108">Sie können verwenden, `EnumerateTypeParameters` Wenn der von [ICorDebugType:: GetType](icordebugtype-gettype-method.md) zurückgegebene CorElementType-Wert ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR oder ELEMENT_TYPE_FNPTR ist.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="f2ab2-109">Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ ab:</span><span class="sxs-lookup"><span data-stu-id="f2ab2-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="f2ab2-110">ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: die Anzahl von Typparametern, die in der enthalten sind, die von `ICorDebugTypeEnum` dieser Methode zurückgegeben wird, hängt von der Anzahl der formalen Typparameter für die entsprechende Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="f2ab2-111">Wenn der Typ z. b. ist `class Dict<String,int32>` , gibt `EnumerateTypeParameters` ein zurück `ICorDebugTypeEnum` , das-Objekte enthält, die `String` und nacheinander darstellen `int32` .</span><span class="sxs-lookup"><span data-stu-id="f2ab2-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="f2ab2-112">ELEMENT_TYPE_FNPTR: die Anzahl der Typparameter, die in der enthalten sind, `ICorDebugTypeEnum` ist ein Wert größer als die Anzahl der von der Funktion akzeptierten Argumente.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="f2ab2-113">Der erste in der enthaltene Typparameter `ICorDebugTypeEnum` ist der Rückgabetyp für die Funktion, und die nachfolgenden Typparameter sind die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="f2ab2-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: ein Typparameter wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2ab2-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="f2ab2-115">Wenn der Typ z. b. ein Arraytyp wie ist `int32[]` , gibt `EnumerateTypeParameters` einen zurück, der `ICorDebugTypeEnum` ein Objekt enthält, das darstellt `int32` .</span><span class="sxs-lookup"><span data-stu-id="f2ab2-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ab2-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f2ab2-116">Requirements</span></span>  

 <span data-ttu-id="f2ab2-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ab2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ab2-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ab2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ab2-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ab2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ab2-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ab2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
