---
title: ICorDebugArrayValue Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a96f2b21e524f03ea3290be268244eaceeb5c7f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408176"
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="73bd8-102">ICorDebugArrayValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="73bd8-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="73bd8-103">Eine Unterklasse von ICorDebugHeapValue, das ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="73bd8-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73bd8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="73bd8-104">Methods</span></span>  
  
|<span data-ttu-id="73bd8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-105">Method</span></span>|<span data-ttu-id="73bd8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73bd8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73bd8-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="73bd8-108">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="73bd8-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="73bd8-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="73bd8-110">Ruft die Gesamtanzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="73bd8-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="73bd8-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="73bd8-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="73bd8-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="73bd8-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="73bd8-114">Ruft einen Wert, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="73bd8-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="73bd8-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="73bd8-116">Ruft das Element an der angegebenen Position, behandelt das Array als ein nullbasiertes, eindimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="73bd8-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="73bd8-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="73bd8-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="73bd8-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="73bd8-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="73bd8-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="73bd8-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="73bd8-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="73bd8-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="73bd8-122">Bestimmt, ob das Array mit Basis Indizes aufweist.</span><span class="sxs-lookup"><span data-stu-id="73bd8-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73bd8-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73bd8-123">Remarks</span></span>  
 <span data-ttu-id="73bd8-124">`ICorDebugArrayValue` unterstützt eindimensionale und mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="73bd8-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73bd8-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="73bd8-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73bd8-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73bd8-126">Requirements</span></span>  
 <span data-ttu-id="73bd8-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73bd8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73bd8-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73bd8-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73bd8-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73bd8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73bd8-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73bd8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bd8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73bd8-131">See Also</span></span>  
 [<span data-ttu-id="73bd8-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="73bd8-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
