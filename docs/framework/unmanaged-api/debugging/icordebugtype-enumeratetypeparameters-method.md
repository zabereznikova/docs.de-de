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
ms.openlocfilehash: 57a82e4ec106fead105cc7f200e7e56026004328
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122383"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="3dccf-102">ICorDebugType::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="3dccf-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="3dccf-103">Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die die <xref:System.Type> Parameter der Klasse enthält, auf die von diesem ICorDebugType verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3dccf-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dccf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dccf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dccf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3dccf-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="3dccf-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugTypeEnum`, der die Parameter des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="3dccf-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dccf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3dccf-107">Remarks</span></span>  
 <span data-ttu-id="3dccf-108">Sie können `EnumerateTypeParameters` verwenden, wenn der von [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) zurückgegebene Wert von "CorElementType" ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR oder ELEMENT_TYPE_FNPTR ist.</span><span class="sxs-lookup"><span data-stu-id="3dccf-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="3dccf-109">Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ ab:</span><span class="sxs-lookup"><span data-stu-id="3dccf-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="3dccf-110">ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: die Anzahl der Typparameter, die in der `ICorDebugTypeEnum` enthalten sind, die von dieser Methode zurückgegeben wird, hängt von der Anzahl der formalen Typparameter für die entsprechende Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="3dccf-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="3dccf-111">Wenn der Typ z. b. `class Dict<String,int32>`ist, gibt `EnumerateTypeParameters` eine `ICorDebugTypeEnum` zurück, die-Objekte enthält, die `String` und `int32` nacheinander darstellen.</span><span class="sxs-lookup"><span data-stu-id="3dccf-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="3dccf-112">ELEMENT_TYPE_FNPTR: die Anzahl der in der `ICorDebugTypeEnum` enthaltenen Typparameter ist ein Wert größer als die Anzahl der von der Funktion akzeptierten Argumente.</span><span class="sxs-lookup"><span data-stu-id="3dccf-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="3dccf-113">Der erste Typparameter, der in der `ICorDebugTypeEnum` enthalten ist, ist der Rückgabetyp für die Funktion, und die nachfolgenden Typparameter sind die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="3dccf-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="3dccf-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: ein Typparameter wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3dccf-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="3dccf-115">Wenn der Typ z. b. ein Arraytyp ist, z. b. `int32[]`, gibt`EnumerateTypeParameters` einen `ICorDebugTypeEnum` zurück, der ein Objekt enthält, das `int32`darstellt.</span><span class="sxs-lookup"><span data-stu-id="3dccf-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dccf-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3dccf-116">Requirements</span></span>  
 <span data-ttu-id="3dccf-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dccf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dccf-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dccf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dccf-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dccf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dccf-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dccf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
