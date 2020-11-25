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
ms.openlocfilehash: ef6cbe2cef3c52d9a4b47ff77e8aeb5159e89c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729758"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="9de4a-102">ICorDebugEval::NewArray-Methode</span><span class="sxs-lookup"><span data-stu-id="9de4a-102">ICorDebugEval::NewArray Method</span></span>

<span data-ttu-id="9de4a-103">Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.</span><span class="sxs-lookup"><span data-stu-id="9de4a-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="9de4a-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="9de4a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9de4a-105">Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9de4a-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de4a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9de4a-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de4a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9de4a-107">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="9de4a-108">in Ein Wert der CorElementType-Enumeration, der den Elementtyp des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="9de4a-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="9de4a-109">in Ein Zeiger auf ein ICorDebugClass-Objekt, das die-Klasse des-Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="9de4a-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="9de4a-110">Dieser Wert kann NULL sein, wenn der Elementtyp ein primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="9de4a-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="9de4a-111">in Die Anzahl der Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="9de4a-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="9de4a-112">In der .NET Framework 2,0 muss dieser Wert 1 lauten.</span><span class="sxs-lookup"><span data-stu-id="9de4a-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="9de4a-113">in Die Größe der einzelnen Dimensionen des Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="9de4a-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="9de4a-114">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="9de4a-114">[in] Optional.</span></span> <span data-ttu-id="9de4a-115">Die untere Grenze jeder Dimension des Arrays.</span><span class="sxs-lookup"><span data-stu-id="9de4a-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="9de4a-116">Wenn dieser Wert weggelassen wird, wird für jede Dimension eine untere Grenze von 0 (null) angenommen.</span><span class="sxs-lookup"><span data-stu-id="9de4a-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de4a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9de4a-117">Remarks</span></span>  

 <span data-ttu-id="9de4a-118">Das Array wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9de4a-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de4a-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9de4a-119">Requirements</span></span>  

 <span data-ttu-id="9de4a-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9de4a-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9de4a-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9de4a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9de4a-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9de4a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9de4a-123">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="9de4a-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
