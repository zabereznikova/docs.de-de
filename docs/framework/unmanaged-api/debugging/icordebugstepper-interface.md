---
title: ICorDebugStepper Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266e8c664ac7c5efa1b199efc522f0b890e38e3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="3fd3e-102">ICorDebugStepper Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="3fd3e-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="3fd3e-103">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fd3e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3fd3e-104">Methods</span></span>  
  
|<span data-ttu-id="3fd3e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-105">Method</span></span>|<span data-ttu-id="3fd3e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fd3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fd3e-107">Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="3fd3e-108">Bewirkt, dass `ICorDebugStepper` mit dem letzten Schrittbefehl Abbrechen sie empfangen.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="3fd3e-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="3fd3e-110">Ruft einen Wert, der angibt, ob dies `ICorDebugStepper` wird derzeit von einem Schritt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="3fd3e-111">SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="3fd3e-112">Legt einen CorDebugIntercept-Wert, der angibt, die Typen von Code, der durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="3fd3e-113">SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="3fd3e-114">Legt einen Wert, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) übergeben Argumentwerte relativ zu den systemeigenen Code oder Microsoft intermediate Language (MSIL)-Code der Methode, die schrittweise durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="3fd3e-115">SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="3fd3e-116">Legt einen CorDebugUnmappedStop-Wert, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="3fd3e-117">Step-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="3fd3e-118">Bewirkt, dass `ICorDebugStepper` , Schritt für Schritt durch den enthaltenden Thread und optional zu fortfahren schrittweises Durchlaufen von Funktionen, die in dem Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="3fd3e-119">StepOut-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="3fd3e-120">Bewirkt, dass `ICorDebugStepper` einstufiger über den enthaltenden Thread und beendet wird, wenn der aktuelle Rahmen ist die Steuerung an den aufrufenden Rahmen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="3fd3e-121">StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd3e-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="3fd3e-122">Bewirkt, dass `ICorDebugStepper` , Schritt für Schritt durch den enthaltenden Thread und zurückzugeben, wenn er Code nach dem letzten von der angegebenen Bereiche erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd3e-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fd3e-123">Remarks</span></span>  
 <span data-ttu-id="3fd3e-124">Die `ICorDebugStepper` Schnittstelle dient den folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="3fd3e-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="3fd3e-125">Sie fungiert als Bezeichner zwischen ein Schrittbefehl, der ausgegeben wird und dem Abschluss dieses Befehls.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="3fd3e-126">Es bietet eine zentrale Schnittstelle zum kapseln alle schrittweise ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="3fd3e-127">Es bietet eine Möglichkeit, einer schrittweisen Ausführung vorzeitig abbrechen.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="3fd3e-128">Es können mehrere zugeordnetem pro Thread vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="3fd3e-129">Beispielsweise kann ein Haltepunkt erreicht werden, während bei einem Prozedurschritt für eine Funktion, und der Benutzer eine neue schrittweisen Ausführung innerhalb der Funktion starten möchten.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="3fd3e-130">Es liegt im Ermessen des Debuggers bestimmen, wie diese Situation zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="3fd3e-131">Der Debugger möchte der ursprünglichen schrittweisen Ausführung abbrechen oder die zwei Vorgänge schachteln.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="3fd3e-132">Die `ICorDebugStepper` Schnittstelle unterstützt beide Optionen.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="3fd3e-133">Eine zugeordnetem kann zwischen Threads migriert werden, wenn die common Language Runtime (CLR) eine threadübergreifend, gemarshallte aufruft.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd3e-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3fd3e-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd3e-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fd3e-135">Requirements</span></span>  
 <span data-ttu-id="3fd3e-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fd3e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd3e-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fd3e-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fd3e-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fd3e-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fd3e-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd3e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd3e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fd3e-140">See Also</span></span>  
 [<span data-ttu-id="3fd3e-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3fd3e-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
