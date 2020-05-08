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
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894967"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="0059e-102">ICorDebugArrayValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0059e-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="0059e-103">Eine Unterklasse von ICorDebugHeapValue, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="0059e-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0059e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0059e-104">Methods</span></span>  
  
|<span data-ttu-id="0059e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-105">Method</span></span>|<span data-ttu-id="0059e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0059e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0059e-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="0059e-108">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="0059e-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="0059e-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="0059e-110">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="0059e-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="0059e-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="0059e-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="0059e-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="0059e-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="0059e-114">Ruft einen Wert ab, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="0059e-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="0059e-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="0059e-116">Ruft das Element an der angegebenen Position ab, wobei das Array als NULL basiertes, eindimensionales Array behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0059e-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="0059e-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="0059e-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="0059e-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="0059e-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="0059e-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="0059e-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="0059e-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="0059e-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="0059e-122">Bestimmt, ob das Array über Basis Indizes verfügt.</span><span class="sxs-lookup"><span data-stu-id="0059e-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0059e-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0059e-123">Remarks</span></span>  
 <span data-ttu-id="0059e-124">`ICorDebugArrayValue`unterstützt sowohl eindimensionale als auch mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="0059e-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0059e-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0059e-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0059e-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0059e-126">Requirements</span></span>  
 <span data-ttu-id="0059e-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0059e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0059e-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0059e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0059e-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0059e-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0059e-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0059e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0059e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0059e-131">See also</span></span>

- [<span data-ttu-id="0059e-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0059e-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
