---
title: ICorDebugEval2::NewParameterizedArray-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf7f8fb0d3418f863f2cd1531dc32b7e64c2b8a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="08961-102">ICorDebugEval2::NewParameterizedArray-Methode</span><span class="sxs-lookup"><span data-stu-id="08961-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="08961-103">Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.</span><span class="sxs-lookup"><span data-stu-id="08961-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08961-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08961-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08961-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08961-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="08961-106">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des im Array gespeicherten Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="08961-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="08961-107">[in] Die Anzahl der Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="08961-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="08961-108">In .NET Framework, Version 2.0 muss dieser Wert 1 sein.</span><span class="sxs-lookup"><span data-stu-id="08961-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="08961-109">[in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="08961-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="08961-110">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="08961-110">[in] Optional.</span></span> <span data-ttu-id="08961-111">Die untere Grenze der einzelnen Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="08961-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="08961-112">Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension angenommen.</span><span class="sxs-lookup"><span data-stu-id="08961-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08961-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08961-113">Remarks</span></span>  
 <span data-ttu-id="08961-114">Die Elemente des Arrays möglicherweise Instanzen eines generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="08961-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="08961-115">Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08961-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="08961-116">In .NET Framework 2.0, den Wert des `rank` muss 1 sein.</span><span class="sxs-lookup"><span data-stu-id="08961-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08961-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08961-117">Requirements</span></span>  
 <span data-ttu-id="08961-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08961-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08961-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08961-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08961-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08961-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08961-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08961-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
