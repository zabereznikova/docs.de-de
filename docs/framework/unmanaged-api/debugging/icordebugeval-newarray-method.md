---
title: ICorDebugEval::NewArray-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="b03fc-102">ICorDebugEval::NewArray-Methode</span><span class="sxs-lookup"><span data-stu-id="b03fc-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="b03fc-103">Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.</span><span class="sxs-lookup"><span data-stu-id="b03fc-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="b03fc-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="b03fc-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b03fc-105">Verwendung [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="b03fc-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03fc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b03fc-106">Syntax</span></span>  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b03fc-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b03fc-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="b03fc-108">[in] Der Wert der CorElementType-Enumeration, die den Elementtyp des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="b03fc-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="b03fc-109">[in] Ein Zeiger auf eine ICorDebugClass-Objekt, das die Klasse des Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="b03fc-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="b03fc-110">Dieser Wert kann null sein, wenn der Elementtyp ein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="b03fc-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="b03fc-111">[in] Die Anzahl der Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="b03fc-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="b03fc-112">In .NET Framework 2.0 muss dieser Wert 1 sein.</span><span class="sxs-lookup"><span data-stu-id="b03fc-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="b03fc-113">[in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b03fc-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="b03fc-114">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="b03fc-114">[in] Optional.</span></span> <span data-ttu-id="b03fc-115">Die untere Grenze der einzelnen Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="b03fc-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="b03fc-116">Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension angenommen.</span><span class="sxs-lookup"><span data-stu-id="b03fc-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b03fc-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b03fc-117">Remarks</span></span>  
 <span data-ttu-id="b03fc-118">Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b03fc-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03fc-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b03fc-119">Requirements</span></span>  
 <span data-ttu-id="b03fc-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b03fc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03fc-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b03fc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b03fc-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03fc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b03fc-123">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b03fc-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
