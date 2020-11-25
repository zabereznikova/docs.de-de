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
ms.openlocfilehash: 343e504e086e740236d7b5977452cc0d789883fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728406"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="69c3b-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69c3b-102">ICorDebugReferenceValue Interface</span></span>

<span data-ttu-id="69c3b-103">Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="69c3b-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="69c3b-104">(Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".</span><span class="sxs-lookup"><span data-stu-id="69c3b-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69c3b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="69c3b-105">Methods</span></span>  
  
|<span data-ttu-id="69c3b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-106">Method</span></span>|<span data-ttu-id="69c3b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69c3b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69c3b-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="69c3b-109">Ruft das Objekt ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="69c3b-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="69c3b-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="69c3b-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="69c3b-111">Not implemented.</span></span> <span data-ttu-id="69c3b-112">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="69c3b-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="69c3b-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="69c3b-114">Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="69c3b-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="69c3b-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="69c3b-116">Ruft einen Wert ab, der angibt `ICorDebugReferenceValue` , ob es sich um einen NULL-Wert handelt. in diesem Fall verweist der `ICorDebugReferenceValue` nicht auf ein-Objekt.</span><span class="sxs-lookup"><span data-stu-id="69c3b-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="69c3b-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3b-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="69c3b-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="69c3b-118">Sets the current memory address.</span></span> <span data-ttu-id="69c3b-119">Das heißt, diese Methode legt diese fest, `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="69c3b-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69c3b-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69c3b-120">Remarks</span></span>  

 <span data-ttu-id="69c3b-121">Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="69c3b-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="69c3b-122">Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="69c3b-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="69c3b-123">Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach der Garbage Collection aktualisiert werden, oder Sie wird vor dem Garbage Collection implizit für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="69c3b-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="69c3b-124">Das `ICorDebugReferenceValue` Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="69c3b-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="69c3b-125">Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="69c3b-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69c3b-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="69c3b-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69c3b-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="69c3b-127">Requirements</span></span>  

 <span data-ttu-id="69c3b-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69c3b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c3b-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69c3b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69c3b-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69c3b-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69c3b-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69c3b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c3b-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69c3b-132">See also</span></span>

- [<span data-ttu-id="69c3b-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="69c3b-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
