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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378351"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="1ca6e-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ca6e-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="1ca6e-103">Stellt Methoden bereit, die einen-Wert verwalten, der ein Verweis auf ein-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="1ca6e-104">(Das heißt, diese Schnittstelle stellt Methoden bereit, die einen-Zeiger verwalten.) Diese Schnittstelle implementiert "ICorDebug Value".</span><span class="sxs-lookup"><span data-stu-id="1ca6e-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ca6e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ca6e-105">Methods</span></span>  
  
|<span data-ttu-id="1ca6e-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-106">Method</span></span>|<span data-ttu-id="1ca6e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ca6e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ca6e-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="1ca6e-109">Ruft das Objekt ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="1ca6e-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="1ca6e-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-111">Not implemented.</span></span> <span data-ttu-id="1ca6e-112">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="1ca6e-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="1ca6e-114">Ruft die aktuelle Speicheradresse des Objekts ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="1ca6e-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="1ca6e-116">Ruft einen Wert ab, der angibt `ICorDebugReferenceValue` , ob es sich um einen NULL-Wert handelt. in diesem Fall verweist der `ICorDebugReferenceValue` nicht auf ein-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="1ca6e-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1ca6e-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="1ca6e-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-118">Sets the current memory address.</span></span> <span data-ttu-id="1ca6e-119">Das heißt, diese Methode legt diese fest, `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ca6e-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ca6e-120">Remarks</span></span>  
 <span data-ttu-id="1ca6e-121">Der Common Language Runtime (CLR) kann eine Garbage Collection für Objekte ausführen, wenn der Debugprozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="1ca6e-122">Der Garbage Collection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="1ca6e-123">Eine `ICorDebugReferenceValue` wird entweder mit der Garbage Collection zusammenarbeiten, damit die Informationen nach der Garbage Collection aktualisiert werden, oder Sie wird vor dem Garbage Collection implizit für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="1ca6e-124">Das `ICorDebugReferenceValue` Objekt kann nach dem Fortsetzen des debuggten Prozesses implizit ungültig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="1ca6e-125">Der abgeleitete "ICorDebugHandleValue" wird erst ungültig, wenn er explizit freigegeben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ca6e-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1ca6e-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ca6e-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1ca6e-127">Requirements</span></span>  
 <span data-ttu-id="1ca6e-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ca6e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ca6e-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ca6e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ca6e-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ca6e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ca6e-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ca6e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca6e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ca6e-132">See also</span></span>

- [<span data-ttu-id="1ca6e-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ca6e-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
