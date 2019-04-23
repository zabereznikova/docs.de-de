---
title: ICorDebugProcess2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b3bb51f307093ea1cc8cc45064d5c405974822
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178021"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="cfc4e-102">ICorDebugProcess2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfc4e-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="cfc4e-103">Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die eine ausgeführten Prozess für verwalteten Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfc4e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cfc4e-104">Methods</span></span>  
  
|<span data-ttu-id="cfc4e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-105">Method</span></span>|<span data-ttu-id="cfc4e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfc4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfc4e-107">ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="cfc4e-108">Entfernt einen Haltepunkt am angegebenen Offset, die von einem früheren Aufruf festgelegt wurde `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="cfc4e-109">GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="cfc4e-110">Ruft die Flags ab, die für die common Language Runtime (CLR) festgelegt werden müssen, um das Image in den Prozess, der auf die dieses laden `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="cfc4e-111">GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="cfc4e-112">Ruft einen Verweiszeiger auf das angegebene verwaltete Objekt, das eine Garbagecollection verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="cfc4e-113">GetThreadForTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="cfc4e-114">Ruft den Thread, der auf dem die Aufgabe mit der angegebenen ID ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="cfc4e-115">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="cfc4e-116">Ruft die Version der CLR auf dem die zu debuggende Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="cfc4e-117">SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="cfc4e-118">Legt die Flags, die für den just-in-Time (JIT)-Compiler zum Laden eines Bilds in der gedebuggte Prozess erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="cfc4e-119">SetUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="cfc4e-120">Legt einen nicht verwaltete Haltepunkt am Offset angegebene systemeigene Image fest.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfc4e-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfc4e-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfc4e-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfc4e-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfc4e-123">Requirements</span></span>  
 <span data-ttu-id="cfc4e-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfc4e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc4e-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfc4e-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfc4e-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfc4e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfc4e-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfc4e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc4e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfc4e-128">See also</span></span>

- [<span data-ttu-id="cfc4e-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cfc4e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
