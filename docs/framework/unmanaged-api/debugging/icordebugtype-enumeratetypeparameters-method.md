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
ms.openlocfilehash: 1b48e375286e709a2ce570769c9a0453765824ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622674"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="d97a5-102">ICorDebugType::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="d97a5-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="d97a5-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die enthält die <xref:System.Type> Parameter von der Klasse, die dieser ICorDebugType verweist.</span><span class="sxs-lookup"><span data-stu-id="d97a5-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d97a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d97a5-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d97a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d97a5-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="d97a5-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugTypeEnum` , die die Parameter des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="d97a5-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d97a5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d97a5-107">Remarks</span></span>  
 <span data-ttu-id="d97a5-108">Sie können `EnumerateTypeParameters` Wenn von der CorElementType-Wert zurückgegeben [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ist ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR oder ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="d97a5-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="d97a5-109">Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ aus:</span><span class="sxs-lookup"><span data-stu-id="d97a5-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="d97a5-110">ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: Die Anzahl von Typparametern, die innerhalb der `ICorDebugTypeEnum` , dass diese Methode zurückgegeben wird, hängt die Anzahl der formalen Typparameter für die entsprechende Klasse.</span><span class="sxs-lookup"><span data-stu-id="d97a5-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="d97a5-111">Wenn der Typ ist z. B. `class Dict<String,int32>`, klicken Sie dann `EnumerateTypeParameters` zurück eine `ICorDebugTypeEnum` , enthält die Objekte, die darstellen `String` und `int32` nacheinander.</span><span class="sxs-lookup"><span data-stu-id="d97a5-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="d97a5-112">ELEMENT_TYPE_FNPTR: Die Anzahl von Typparametern, die innerhalb der `ICorDebugTypeEnum` können größer als die Anzahl von Argumenten, die von der Funktion akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d97a5-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="d97a5-113">Der erste Typparameter, die innerhalb der `ICorDebugTypeEnum` ist der Rückgabetyp der Funktion und die nachfolgende Typparameter werden Funktionsparameter.</span><span class="sxs-lookup"><span data-stu-id="d97a5-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="d97a5-114">ELEMENT_TYPE_ARRAY ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: Ein Typparameter wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d97a5-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="d97a5-115">Wenn der Typ einen Arraytyp ist, wie z. B. `int32[]`,`EnumerateTypeParameters` gibt ein `ICorDebugTypeEnum` , enthält ein Objekt zur Darstellung `int32`.</span><span class="sxs-lookup"><span data-stu-id="d97a5-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d97a5-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d97a5-116">Requirements</span></span>  
 <span data-ttu-id="d97a5-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d97a5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d97a5-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d97a5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d97a5-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d97a5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d97a5-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d97a5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
