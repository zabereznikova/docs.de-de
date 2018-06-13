---
title: ICorDebugReferenceValue Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6cdfa9f3717e4025ff6f4fe6da3c1457cdebf7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422330"
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="d4020-102">ICorDebugReferenceValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="d4020-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="d4020-103">Enthält Methoden, die einen Wert zu verwalten, der einen Verweis auf ein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d4020-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="d4020-104">(D. h. diese Schnittstelle stellt Methoden bereit, die einen Zeiger zu verwalten.) Diese Schnittstelle implementiert "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="d4020-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4020-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d4020-105">Methods</span></span>  
  
|<span data-ttu-id="d4020-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-106">Method</span></span>|<span data-ttu-id="d4020-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4020-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4020-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="d4020-109">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d4020-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="d4020-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="d4020-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="d4020-111">Not implemented.</span></span> <span data-ttu-id="d4020-112">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="d4020-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="d4020-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="d4020-114">Ruft die aktuelle Speicheradresse des referenzierten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="d4020-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="d4020-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="d4020-116">Ruft einen Wert, der angibt, ob dies `ICorDebugReferenceValue` ein null-Wert in diesem Fall wird die `ICorDebugReferenceValue` verweist nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="d4020-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="d4020-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d4020-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="d4020-118">Legt die aktuelle Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="d4020-118">Sets the current memory address.</span></span> <span data-ttu-id="d4020-119">D. h. diese Methode legt für diesen `ICorDebugReferenceValue` auf ein Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4020-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4020-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4020-120">Remarks</span></span>  
 <span data-ttu-id="d4020-121">Die common Language Runtime (CLR) möglicherweise eine Garbagecollection Objekte führen, wenn es sich bei ein debuggten Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d4020-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="d4020-122">Die Garbagecollection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="d4020-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="d4020-123">Ein `ICorDebugReferenceValue` werden entweder zusammen mit der Garbagecollection, damit die Informationen nach der Garbagecollection aktualisiert werden, oder er wird implizit vor der Garbagecollection ungültig gemacht.</span><span class="sxs-lookup"><span data-stu-id="d4020-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="d4020-124">Die `ICorDebugReferenceValue` Objekt möglicherweise implizit ungültig gemacht, nachdem der debuggten Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="d4020-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="d4020-125">Der abgeleitete "ICorDebugHandleValue" ist nicht für ungültig erklärt, bis er explizit freigegeben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="d4020-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4020-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4020-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4020-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4020-127">Requirements</span></span>  
 <span data-ttu-id="d4020-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4020-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4020-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4020-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4020-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4020-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4020-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4020-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4020-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4020-132">See Also</span></span>  
    
    
 [<span data-ttu-id="d4020-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4020-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
