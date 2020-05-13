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
ms.openlocfilehash: 622fdfa37c93e406950e73941775828ae4b112fa
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379420"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="57371-102">ICorDebugStepper-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57371-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="57371-103">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="57371-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57371-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="57371-104">Methods</span></span>  
  
|<span data-ttu-id="57371-105">Methode</span><span class="sxs-lookup"><span data-stu-id="57371-105">Method</span></span>|<span data-ttu-id="57371-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57371-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57371-107">Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-107">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="57371-108">Dies bewirkt `ICorDebugStepper` , dass der letzte Schritt Befehl abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="57371-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="57371-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-109">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="57371-110">Ruft einen Wert ab, der angibt, ob dieser `ICorDebugStepper` gerade einen Schritt ausführt.</span><span class="sxs-lookup"><span data-stu-id="57371-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="57371-111">SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-111">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="57371-112">Legt einen CorDebugIntercept-Wert fest, der die Typen von Code angibt, die in Einzelschritten werden.</span><span class="sxs-lookup"><span data-stu-id="57371-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="57371-113">SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-113">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="57371-114">Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) Argument Werte in Bezug auf den systemeigenen Code oder den MSIL-Code (Microsoft Intermediate Language) der Methode übergeben, die durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="57371-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="57371-115">SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-115">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="57371-116">Legt einen CorDebugUnmappedStop-Wert fest, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="57371-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="57371-117">Step-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-117">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="57371-118">Bewirkt, `ICorDebugStepper` dass dieser den enthaltenden Thread schrittweise durchläuft, und optional, um die Einzelschritt Weise durch Funktionen fortzusetzen, die innerhalb des Threads aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="57371-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="57371-119">StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-119">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="57371-120">Bewirkt, dass dieser `ICorDebugStepper` den enthaltenden Thread in einem Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="57371-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="57371-121">StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="57371-121">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="57371-122">Bewirkt, dass dieser `ICorDebugStepper` den enthaltenden Thread in einen Schritt einschlägt und zurückgibt, wenn er Code über den letzten der angegebenen Bereiche hinaus erreicht.</span><span class="sxs-lookup"><span data-stu-id="57371-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57371-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57371-123">Remarks</span></span>  
 <span data-ttu-id="57371-124">Die- `ICorDebugStepper` Schnittstelle dient folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="57371-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="57371-125">Er fungiert als Bezeichner zwischen einem ausgegebene Schritt Befehl und dem Abschluss dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="57371-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="57371-126">Sie stellt eine zentrale Schnittstelle zum Kapseln der gesamten schrittweise bereit, die ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="57371-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="57371-127">Es bietet eine Möglichkeit, einen schrittweise Abbruch abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="57371-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="57371-128">Pro Thread kann mehr als ein Stepper vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="57371-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="57371-129">Beispielsweise kann ein Haltepunkt beim Durchlaufen einer Funktion gedrückt werden, und der Benutzer möchte einen neuen Schritt Vorgang innerhalb dieser Funktion starten.</span><span class="sxs-lookup"><span data-stu-id="57371-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="57371-130">Der Debugger kann feststellen, wie diese Situation behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="57371-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="57371-131">Der Debugger kann den ursprünglichen Schritt Vorgang abbrechen oder die beiden Vorgänge schachteln.</span><span class="sxs-lookup"><span data-stu-id="57371-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="57371-132">Die- `ICorDebugStepper` Schnittstelle unterstützt beide Optionen.</span><span class="sxs-lookup"><span data-stu-id="57371-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="57371-133">Ein Stepper kann zwischen Threads migriert werden, wenn die Common Language Runtime (CLR) einen Thread übergreifenden, gemarshallten Aufrufvorgang durchführt.</span><span class="sxs-lookup"><span data-stu-id="57371-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57371-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="57371-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57371-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="57371-135">Requirements</span></span>  
 <span data-ttu-id="57371-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57371-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57371-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57371-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57371-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57371-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57371-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57371-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57371-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57371-140">See also</span></span>

- [<span data-ttu-id="57371-141">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="57371-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
