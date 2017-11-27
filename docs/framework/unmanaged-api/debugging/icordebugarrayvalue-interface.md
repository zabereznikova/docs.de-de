---
title: ICorDebugArrayValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="4dfe6-102">ICorDebugArrayValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="4dfe6-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="4dfe6-103">Eine Unterklasse von ICorDebugHeapValue, das ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4dfe6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4dfe6-104">Methods</span></span>  
  
|<span data-ttu-id="4dfe6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-105">Method</span></span>|<span data-ttu-id="4dfe6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4dfe6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4dfe6-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="4dfe6-108">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="4dfe6-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="4dfe6-110">Ruft die Gesamtanzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="4dfe6-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="4dfe6-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="4dfe6-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="4dfe6-114">Ruft einen Wert, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="4dfe6-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="4dfe6-116">Ruft das Element an der angegebenen Position, behandelt das Array als ein nullbasiertes, eindimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="4dfe6-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="4dfe6-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="4dfe6-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="4dfe6-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="4dfe6-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="4dfe6-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="4dfe6-122">Bestimmt, ob das Array mit Basis Indizes aufweist.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dfe6-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4dfe6-123">Remarks</span></span>  
 <span data-ttu-id="4dfe6-124">`ICorDebugArrayValue`unterstützt eindimensionale und mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dfe6-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4dfe6-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dfe6-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dfe6-126">Requirements</span></span>  
 <span data-ttu-id="4dfe6-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dfe6-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dfe6-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dfe6-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dfe6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dfe6-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dfe6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfe6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dfe6-131">See Also</span></span>  
 [<span data-ttu-id="4dfe6-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4dfe6-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
