---
title: ICorDebugStepper-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f1d94ffde71962c848bece808bf2d982093896a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652164"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="9e049-102">ICorDebugStepper-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e049-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="9e049-103">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="9e049-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e049-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9e049-104">Methods</span></span>  
  
|<span data-ttu-id="9e049-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-105">Method</span></span>|<span data-ttu-id="9e049-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e049-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e049-107">Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="9e049-108">Bewirkt, dass dieser `ICorDebugStepper` , mit dem letzten Schrittbefehl abzubrechen, er empfangen.</span><span class="sxs-lookup"><span data-stu-id="9e049-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="9e049-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="9e049-110">Ruft einen Wert, der angibt, ob dies `ICorDebugStepper` aktuell einen Schritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9e049-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="9e049-111">SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="9e049-112">Legt einen CorDebugIntercept-Wert, der angibt, die Typen von Code, der durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e049-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="9e049-113">SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="9e049-114">Legt einen Wert, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) Argumentwerte, die relativ zu den systemeigenen Code oder Code für Microsoft intermediate Language (MSIL) der Methode, die schrittweise durchlaufen wird übergeben.</span><span class="sxs-lookup"><span data-stu-id="9e049-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="9e049-115">SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="9e049-116">Legt einen CorDebugUnmappedStop-Wert, der den Typ von nicht zugeordnetem Code gibt an, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="9e049-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="9e049-117">Step-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="9e049-118">Bewirkt, dass dieser `ICorDebugStepper` , Schritt für Schritt durch den enthaltenen Thread und (optional) um weiterhin schrittweises Durchlaufen von Funktionen, in dem Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e049-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="9e049-119">StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="9e049-120">Bewirkt, dass dieser `ICorDebugStepper` Schritt für Schritt durch den enthaltenen Thread und beendet wird, wenn der aktuelle Frame die steuerelementrückgabe an den aufrufenden Rahmen.</span><span class="sxs-lookup"><span data-stu-id="9e049-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="9e049-121">StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="9e049-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="9e049-122">Bewirkt, dass dieser `ICorDebugStepper` , Schritt für Schritt durch den enthaltenen Thread und zurückzugeben, wenn sie Code nach dem letzten von der angegebenen Bereiche erreicht.</span><span class="sxs-lookup"><span data-stu-id="9e049-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e049-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e049-123">Remarks</span></span>  
 <span data-ttu-id="9e049-124">Die `ICorDebugStepper` -Schnittstelle dient folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="9e049-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="9e049-125">Er fungiert als Bezeichner zwischen ein Schrittbefehl, der ausgegeben wird und dem Abschluss dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="9e049-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="9e049-126">Es bietet eine zentrale Schnittstelle zum kapseln alle das schrittweise durchlaufen, die ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="9e049-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="9e049-127">Es bietet eine Möglichkeit, einer schrittweisen Ausführung vorzeitig abbrechen.</span><span class="sxs-lookup"><span data-stu-id="9e049-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="9e049-128">Es können mehrere zugeordnetem pro Thread vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="9e049-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="9e049-129">Z. B. ein Haltepunkt erreicht werden kann, während bei einem Prozedurschritt für eine Funktion, und der Benutzer eine neue schrittweisen Ausführung innerhalb dieser Funktion beginnen möchten.</span><span class="sxs-lookup"><span data-stu-id="9e049-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="9e049-130">Es ist Aufgabe des Debuggers zu bestimmen, wie für diese Situation.</span><span class="sxs-lookup"><span data-stu-id="9e049-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="9e049-131">Der Debugger sollten die ursprünglichen schrittweisen Ausführung abbrechen oder Schachteln von beiden Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="9e049-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="9e049-132">Die `ICorDebugStepper` Schnittstelle unterstützt beides.</span><span class="sxs-lookup"><span data-stu-id="9e049-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="9e049-133">Eine zugeordnetem kann zwischen Threads migrieren, wenn die common Language Runtime (CLR) Cross-Thread, gemarshallten aufruft.</span><span class="sxs-lookup"><span data-stu-id="9e049-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e049-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e049-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e049-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e049-135">Requirements</span></span>  
 <span data-ttu-id="9e049-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e049-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e049-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e049-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e049-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e049-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e049-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e049-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e049-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e049-140">See also</span></span>

- [<span data-ttu-id="9e049-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e049-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
