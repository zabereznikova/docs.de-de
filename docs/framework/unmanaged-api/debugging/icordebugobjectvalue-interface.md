---
title: ICorDebugObjectValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6dfde9f212936b1a0d0f5a6e76eafd4a2e62356c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="d51e6-102">ICorDebugObjectValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="d51e6-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="d51e6-103">Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d51e6-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d51e6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d51e6-104">Methods</span></span>  
  
|<span data-ttu-id="d51e6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-105">Method</span></span>|<span data-ttu-id="d51e6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d51e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d51e6-107">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="d51e6-108">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) <xref:System.Type> des Objekts, die von diesem `ICorDebugObjectValue` Verweise.</span><span class="sxs-lookup"><span data-stu-id="d51e6-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="d51e6-109">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="d51e6-110">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="d51e6-110">Not implemented.</span></span>|  
|[<span data-ttu-id="d51e6-111">GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="d51e6-112">Ruft einen Schnittstellenzeiger auf eine [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , das den Wert des angegebenen Felds der angegebenen Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="d51e6-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="d51e6-113">GetManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="d51e6-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="d51e6-114">Obsolete.</span></span> <span data-ttu-id="d51e6-115">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="d51e6-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="d51e6-116">GetVirtualMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="d51e6-117">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="d51e6-117">Not implemented.</span></span>|  
|[<span data-ttu-id="d51e6-118">IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="d51e6-119">Ruft einen Wert, der angibt, ob das Objekt verweist, der dies `ICorDebugObjectValue` ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="d51e6-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="d51e6-120">SetFromManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="d51e6-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="d51e6-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="d51e6-121">Obsolete.</span></span> <span data-ttu-id="d51e6-122">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="d51e6-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d51e6-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d51e6-123">Remarks</span></span>  
 <span data-ttu-id="d51e6-124">Ein `ICorDebugObjectValue` bleibt gültig, bis der zu debuggende Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d51e6-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d51e6-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d51e6-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d51e6-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d51e6-126">Requirements</span></span>  
 <span data-ttu-id="d51e6-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d51e6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d51e6-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d51e6-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d51e6-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d51e6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d51e6-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d51e6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51e6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d51e6-131">See Also</span></span>  
 [<span data-ttu-id="d51e6-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d51e6-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
