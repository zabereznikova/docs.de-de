---
title: ICorDebugReferenceValue-Schnittstelle
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
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965645"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="1a6b1-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a6b1-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="1a6b1-103">Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="1a6b1-104">(Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".</span><span class="sxs-lookup"><span data-stu-id="1a6b1-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a6b1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1a6b1-105">Methods</span></span>  
  
|<span data-ttu-id="1a6b1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-106">Method</span></span>|<span data-ttu-id="1a6b1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a6b1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a6b1-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="1a6b1-109">Ruft das Objekt ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="1a6b1-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="1a6b1-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-111">Not implemented.</span></span> <span data-ttu-id="1a6b1-112">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="1a6b1-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="1a6b1-114">Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="1a6b1-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="1a6b1-116">Ruft einen Wert ab, der angibt `ICorDebugReferenceValue` , ob es sich um einen NULL-Wert `ICorDebugReferenceValue` handelt. in diesem Fall verweist der nicht auf ein-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="1a6b1-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1a6b1-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="1a6b1-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-118">Sets the current memory address.</span></span> <span data-ttu-id="1a6b1-119">Das heißt, diese Methode legt diese `ICorDebugReferenceValue` fest, um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a6b1-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a6b1-120">Remarks</span></span>  
 <span data-ttu-id="1a6b1-121">Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="1a6b1-122">Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="1a6b1-123">Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach der Garbage Collection aktualisiert werden, oder Sie wird vor dem Garbage Collection implizit für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="1a6b1-124">Das `ICorDebugReferenceValue` Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="1a6b1-125">Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a6b1-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a6b1-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a6b1-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a6b1-127">Requirements</span></span>  
 <span data-ttu-id="1a6b1-128">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a6b1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a6b1-129">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1a6b1-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a6b1-130">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a6b1-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a6b1-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a6b1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a6b1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a6b1-132">See also</span></span>

- [<span data-ttu-id="1a6b1-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1a6b1-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
