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
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792132"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="f8117-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8117-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="f8117-103">Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="f8117-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="f8117-104">(Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".</span><span class="sxs-lookup"><span data-stu-id="f8117-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8117-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8117-105">Methods</span></span>  
  
|<span data-ttu-id="f8117-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-106">Method</span></span>|<span data-ttu-id="f8117-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8117-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8117-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="f8117-109">Ruft das Objekt ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f8117-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="f8117-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="f8117-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8117-111">Not implemented.</span></span> <span data-ttu-id="f8117-112">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f8117-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="f8117-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="f8117-114">Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f8117-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="f8117-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="f8117-116">Ruft einen Wert ab, der angibt, ob dieses `ICorDebugReferenceValue` ein NULL-Wert ist. in diesem Fall zeigt der `ICorDebugReferenceValue` nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="f8117-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="f8117-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f8117-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="f8117-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="f8117-118">Sets the current memory address.</span></span> <span data-ttu-id="f8117-119">Das heißt, diese Methode legt diese `ICorDebugReferenceValue` fest, um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f8117-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8117-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8117-120">Remarks</span></span>  
 <span data-ttu-id="f8117-121">Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f8117-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="f8117-122">Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="f8117-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="f8117-123">Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach dem Garbage Collection aktualisiert werden, oder Sie wird vor der Garbage Collection implizit für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="f8117-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="f8117-124">Das `ICorDebugReferenceValue`-Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f8117-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="f8117-125">Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="f8117-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8117-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f8117-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8117-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8117-127">Requirements</span></span>  
 <span data-ttu-id="f8117-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8117-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8117-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8117-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8117-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8117-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8117-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8117-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8117-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8117-132">See also</span></span>

- [<span data-ttu-id="f8117-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8117-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
