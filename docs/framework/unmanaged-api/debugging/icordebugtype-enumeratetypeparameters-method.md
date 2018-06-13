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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12b002aaad65fd5f2a1207700c8de2ca8dd60eec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421878"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="ab3cf-102">ICorDebugType::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="ab3cf-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="ab3cf-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die enthält die <xref:System.Type> Parameter von der Klasse, die dieser ICorDebugType verweist.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab3cf-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab3cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab3cf-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="ab3cf-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugTypeEnum` , die die Parameter des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab3cf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab3cf-107">Remarks</span></span>  
 <span data-ttu-id="ab3cf-108">Können Sie `EnumerateTypeParameters` , wenn der CorElementType-durch Rückgabewert [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, einem, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ ist PTR oder ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="ab3cf-109">Die Anzahl von Parametern und deren Reihenfolge hängt vom Typ:</span><span class="sxs-lookup"><span data-stu-id="ab3cf-109">The number of parameters and their order depends on the type:</span></span>  
  
-   <span data-ttu-id="ab3cf-110">ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: die Anzahl von Typparametern, die in enthaltenen der `ICorDebugTypeEnum` , dass diese Methode zurückgibt, hängt die Anzahl der formalen Parameter für die entsprechende Klasse.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="ab3cf-111">Z. B., wenn der Typ ist `class Dict<String,int32>`, klicken Sie dann `EnumerateTypeParameters` zurück ein `ICorDebugTypeEnum` , die Objekte, die darstellt enthält `String` und `int32` nacheinander.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
-   <span data-ttu-id="ab3cf-112">ELEMENT_TYPE_FNPTR: Die Anzahl von Typparametern, die in enthaltenen der `ICorDebugTypeEnum` ist um eins größer als die Anzahl von Argumenten akzeptiert, die von der Funktion.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="ab3cf-113">Der erste Typparameter, der in enthalten die `ICorDebugTypeEnum` ist der Rückgabetyp für die Funktion und die nachfolgenden Typparameter sind den Funktionsparametern.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
-   <span data-ttu-id="ab3cf-114">Einem ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: ein Typparameter wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="ab3cf-115">Angenommen, wenn der Typ ein Arraytyp ist, z. B. `int32[]`,`EnumerateTypeParameters` zurück ein `ICorDebugTypeEnum` , enthält ein Objekt darstellt, `int32`.</span><span class="sxs-lookup"><span data-stu-id="ab3cf-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab3cf-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab3cf-116">Requirements</span></span>  
 <span data-ttu-id="ab3cf-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab3cf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab3cf-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab3cf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab3cf-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab3cf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab3cf-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab3cf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
