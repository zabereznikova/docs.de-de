---
title: ICorDebugArrayValue-Schnittstelle
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
ms.openlocfilehash: 73898bf5f4303d677787bae587a16f2f325dee9e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970843"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="e980d-102">ICorDebugArrayValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e980d-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="e980d-103">Eine Unterklasse von ICorDebugHeapValue, das ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="e980d-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e980d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e980d-104">Methods</span></span>  
  
|<span data-ttu-id="e980d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-105">Method</span></span>|<span data-ttu-id="e980d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e980d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e980d-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="e980d-108">Ruft den Basisindex für jede Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="e980d-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="e980d-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="e980d-110">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="e980d-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="e980d-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="e980d-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="e980d-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="e980d-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="e980d-114">Ruft einen Wert, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="e980d-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="e980d-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="e980d-116">Ruft das Element an der angegebenen Position, behandelt das Array als ein nullbasiertes, eindimensionales Array.</span><span class="sxs-lookup"><span data-stu-id="e980d-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="e980d-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="e980d-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="e980d-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="e980d-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="e980d-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="e980d-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="e980d-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="e980d-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="e980d-122">Bestimmt, ob das Array Basis Indizes aufweist.</span><span class="sxs-lookup"><span data-stu-id="e980d-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e980d-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e980d-123">Remarks</span></span>  
 <span data-ttu-id="e980d-124">`ICorDebugArrayValue` unterstützt sowohl ein-als auch mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="e980d-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e980d-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e980d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e980d-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e980d-126">Requirements</span></span>  
 <span data-ttu-id="e980d-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e980d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e980d-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e980d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e980d-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e980d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e980d-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e980d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e980d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e980d-131">See also</span></span>
- [<span data-ttu-id="e980d-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e980d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
