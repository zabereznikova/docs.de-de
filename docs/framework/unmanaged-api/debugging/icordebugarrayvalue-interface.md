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
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778205"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="f67ad-102">ICorDebugArrayValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f67ad-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="f67ad-103">Eine Unterklasse von ICorDebugHeapValue, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="f67ad-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f67ad-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f67ad-104">Methods</span></span>  
  
|<span data-ttu-id="f67ad-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-105">Method</span></span>|<span data-ttu-id="f67ad-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f67ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f67ad-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="f67ad-108">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="f67ad-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="f67ad-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="f67ad-110">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="f67ad-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="f67ad-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="f67ad-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="f67ad-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="f67ad-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="f67ad-114">Ruft einen Wert ab, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="f67ad-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="f67ad-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="f67ad-116">Ruft das Element an der angegebenen Position ab, wobei das Array als NULL basiertes, eindimensionales Array behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="f67ad-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="f67ad-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="f67ad-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="f67ad-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="f67ad-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="f67ad-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="f67ad-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="f67ad-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="f67ad-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="f67ad-122">Bestimmt, ob das Array über Basis Indizes verfügt.</span><span class="sxs-lookup"><span data-stu-id="f67ad-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f67ad-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f67ad-123">Remarks</span></span>  
 <span data-ttu-id="f67ad-124">`ICorDebugArrayValue` unterstützt sowohl eindimensionale als auch mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="f67ad-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f67ad-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f67ad-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f67ad-126">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f67ad-126">Requirements</span></span>  
 <span data-ttu-id="f67ad-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f67ad-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f67ad-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f67ad-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f67ad-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f67ad-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f67ad-130">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f67ad-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f67ad-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f67ad-131">See also</span></span>

- [<span data-ttu-id="f67ad-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f67ad-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
