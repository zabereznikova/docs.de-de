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
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207480"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="1f10f-102">ICorDebugObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f10f-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="1f10f-103">Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1f10f-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f10f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1f10f-104">Methods</span></span>  
  
|<span data-ttu-id="1f10f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-105">Method</span></span>|<span data-ttu-id="1f10f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f10f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f10f-107">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="1f10f-108">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR) <xref:System.Type> des-Objekts ab, auf das dieser `ICorDebugObjectValue` verweist.</span><span class="sxs-lookup"><span data-stu-id="1f10f-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="1f10f-109">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="1f10f-110">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1f10f-110">Not implemented.</span></span>|  
|[<span data-ttu-id="1f10f-111">GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="1f10f-112">Ruft einen Schnittstellen Zeiger auf einen [ICorDebugValue](icordebugvalue-interface.md) ab, der den Wert des angegebenen Felds der angegebenen Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f10f-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="1f10f-113">GetManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="1f10f-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1f10f-114">Obsolete.</span></span> <span data-ttu-id="1f10f-115">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="1f10f-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="1f10f-116">GetVirtualMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="1f10f-117">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1f10f-117">Not implemented.</span></span>|  
|[<span data-ttu-id="1f10f-118">IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="1f10f-119">Ruft einen Wert ab, der angibt, ob das Objekt, auf das dieser verweist, `ICorDebugObjectValue` ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="1f10f-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="1f10f-120">SetFromManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="1f10f-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="1f10f-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1f10f-121">Obsolete.</span></span> <span data-ttu-id="1f10f-122">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="1f10f-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f10f-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f10f-123">Remarks</span></span>  
 <span data-ttu-id="1f10f-124">Ein `ICorDebugObjectValue` bleibt gültig, bis der Prozess, der debuggt wird, fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1f10f-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f10f-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f10f-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f10f-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1f10f-126">Requirements</span></span>  
 <span data-ttu-id="1f10f-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f10f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f10f-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f10f-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f10f-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f10f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f10f-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f10f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f10f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f10f-131">See also</span></span>

- [<span data-ttu-id="1f10f-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1f10f-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
