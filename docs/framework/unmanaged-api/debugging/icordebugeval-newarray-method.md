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
ms.openlocfilehash: 13ac5379992f4e768b09a03d31591143ba9bf627
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788726"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="b9eae-102">ICorDebugEval::NewArray-Methode</span><span class="sxs-lookup"><span data-stu-id="b9eae-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="b9eae-103">Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.</span><span class="sxs-lookup"><span data-stu-id="b9eae-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="b9eae-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="b9eae-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b9eae-105">Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b9eae-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9eae-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9eae-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9eae-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="b9eae-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="b9eae-108">in Ein Wert der CorElementType-Enumeration, der den Elementtyp des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="b9eae-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="b9eae-109">[in] Ein Zeiger auf eine ICorDebugClass-Objekt, das die Klasse des Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="b9eae-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="b9eae-110">Dieser Wert kann NULL sein, wenn der Elementtyp ein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="b9eae-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="b9eae-111">in Die Anzahl der Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="b9eae-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="b9eae-112">In der .NET Framework 2,0 muss dieser Wert 1 lauten.</span><span class="sxs-lookup"><span data-stu-id="b9eae-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="b9eae-113">in Die Größe der einzelnen Dimensionen des Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9eae-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="b9eae-114">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="b9eae-114">[in] Optional.</span></span> <span data-ttu-id="b9eae-115">Die untere Grenze jeder Dimension des Arrays.</span><span class="sxs-lookup"><span data-stu-id="b9eae-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="b9eae-116">Wenn dieser Wert weggelassen wird, wird für jede Dimension eine untere Grenze von 0 (null) angenommen.</span><span class="sxs-lookup"><span data-stu-id="b9eae-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9eae-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9eae-117">Remarks</span></span>  
 <span data-ttu-id="b9eae-118">Das Array wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9eae-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9eae-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9eae-119">Requirements</span></span>  
 <span data-ttu-id="b9eae-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9eae-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9eae-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9eae-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9eae-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9eae-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9eae-123">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="b9eae-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
