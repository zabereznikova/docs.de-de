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
ms.openlocfilehash: 99bd3e9ae1faec1b71933681fadf4816b4789c98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952207"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="982ca-102">ICorDebugArrayValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="982ca-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="982ca-103">Eine Unterklasse von ICorDebugHeapValue, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="982ca-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="982ca-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="982ca-104">Methods</span></span>  
  
|<span data-ttu-id="982ca-105">Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-105">Method</span></span>|<span data-ttu-id="982ca-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="982ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="982ca-107">GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="982ca-108">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="982ca-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="982ca-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="982ca-110">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="982ca-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="982ca-111">GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="982ca-112">Ruft die Dimensionen des Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="982ca-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="982ca-113">GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="982ca-114">Ruft einen Wert ab, der das angegebene Element im Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="982ca-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="982ca-115">GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="982ca-116">Ruft das Element an der angegebenen Position ab, wobei das Array als NULL basiertes, eindimensionales Array behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="982ca-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="982ca-117">GetElementType-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="982ca-118">Ruft den einfachen Typ der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="982ca-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="982ca-119">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="982ca-120">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="982ca-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="982ca-121">HasBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="982ca-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="982ca-122">Bestimmt, ob das Array über Basis Indizes verfügt.</span><span class="sxs-lookup"><span data-stu-id="982ca-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="982ca-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="982ca-123">Remarks</span></span>  
 <span data-ttu-id="982ca-124">`ICorDebugArrayValue`unterstützt sowohl eindimensionale als auch mehrdimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="982ca-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="982ca-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="982ca-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="982ca-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="982ca-126">Requirements</span></span>  
 <span data-ttu-id="982ca-127">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="982ca-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="982ca-128">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="982ca-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="982ca-129">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="982ca-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="982ca-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982ca-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="982ca-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="982ca-131">See also</span></span>

- [<span data-ttu-id="982ca-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="982ca-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
