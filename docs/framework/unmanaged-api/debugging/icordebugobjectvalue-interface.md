---
title: ICorDebugObjectValue-Schnittstelle
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
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222613"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="80311-102">ICorDebugObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80311-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="80311-103">Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="80311-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80311-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="80311-104">Methods</span></span>  
  
|<span data-ttu-id="80311-105">Methode</span><span class="sxs-lookup"><span data-stu-id="80311-105">Method</span></span>|<span data-ttu-id="80311-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80311-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80311-107">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="80311-108">Ruft einen Schnittstellenzeiger für die common Language Runtime (CLR) <xref:System.Type> des Objekts, das von diesem `ICorDebugObjectValue` verweisen.</span><span class="sxs-lookup"><span data-stu-id="80311-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="80311-109">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="80311-110">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="80311-110">Not implemented.</span></span>|  
|[<span data-ttu-id="80311-111">GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="80311-112">Ruft einen Schnittstellenzeiger auf ein [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , das den Wert des angegebenen Felds der angegebenen Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="80311-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="80311-113">GetManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="80311-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="80311-114">Obsolete.</span></span> <span data-ttu-id="80311-115">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="80311-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="80311-116">GetVirtualMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="80311-117">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="80311-117">Not implemented.</span></span>|  
|[<span data-ttu-id="80311-118">IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="80311-119">Ruft einen Wert, der angibt, ob das Objekt verweist, der diese `ICorDebugObjectValue` ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="80311-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="80311-120">SetFromManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="80311-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="80311-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="80311-121">Obsolete.</span></span> <span data-ttu-id="80311-122">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="80311-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80311-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80311-123">Remarks</span></span>  
 <span data-ttu-id="80311-124">Ein `ICorDebugObjectValue` bleibt gültig, bis der Debugvorgang fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="80311-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80311-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="80311-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80311-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80311-126">Requirements</span></span>  
 <span data-ttu-id="80311-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80311-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80311-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80311-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80311-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80311-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="80311-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="80311-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80311-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80311-131">See also</span></span>

- [<span data-ttu-id="80311-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="80311-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
