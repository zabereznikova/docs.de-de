---
title: ICorDebugObjectValue-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd991049c159b96a0f0717b31d6a2834b250f70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631988"
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="a1340-102">ICorDebugObjectValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="a1340-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="a1340-103">Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a1340-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1340-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a1340-104">Methods</span></span>  
  
|<span data-ttu-id="a1340-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-105">Method</span></span>|<span data-ttu-id="a1340-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1340-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1340-107">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="a1340-108">Ruft einen Schnittstellenzeiger für die common Language Runtime (CLR) <xref:System.Type> des Objekts, das von diesem `ICorDebugObjectValue` verweisen.</span><span class="sxs-lookup"><span data-stu-id="a1340-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="a1340-109">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="a1340-110">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a1340-110">Not implemented.</span></span>|  
|[<span data-ttu-id="a1340-111">GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="a1340-112">Ruft einen Schnittstellenzeiger auf ein [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , das den Wert des angegebenen Felds der angegebenen Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1340-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="a1340-113">GetManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="a1340-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a1340-114">Obsolete.</span></span> <span data-ttu-id="a1340-115">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="a1340-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="a1340-116">GetVirtualMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="a1340-117">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a1340-117">Not implemented.</span></span>|  
|[<span data-ttu-id="a1340-118">IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="a1340-119">Ruft einen Wert, der angibt, ob das Objekt verweist, der diese `ICorDebugObjectValue` ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="a1340-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="a1340-120">SetFromManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="a1340-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="a1340-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a1340-121">Obsolete.</span></span> <span data-ttu-id="a1340-122">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="a1340-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1340-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1340-123">Remarks</span></span>  
 <span data-ttu-id="a1340-124">Ein `ICorDebugObjectValue` bleibt gültig, bis der Debugvorgang fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a1340-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1340-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a1340-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1340-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1340-126">Requirements</span></span>  
 <span data-ttu-id="a1340-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1340-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1340-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1340-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1340-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1340-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1340-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1340-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1340-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1340-131">See also</span></span>
- [<span data-ttu-id="a1340-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1340-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

