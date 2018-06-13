---
title: ICorDebugProcess2 Schnittstelle1
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
ms.openlocfilehash: 6a1588a37891d6a73c49cb1b9ccbc81d9dcdb7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420416"
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="bca83-102">ICorDebugProcess2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="bca83-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="bca83-103">Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die eine Prozess Ausführung von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="bca83-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bca83-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bca83-104">Methods</span></span>  
  
|<span data-ttu-id="bca83-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-105">Method</span></span>|<span data-ttu-id="bca83-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bca83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bca83-107">ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="bca83-108">Entfernt einen Haltepunkt am angegebenen Offset begonnen, die durch einen früheren Aufruf festgelegter `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="bca83-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="bca83-109">GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="bca83-110">Ruft die Flags ab, die für die common Language Runtime (CLR) müssen, beim Laden des Bilds in den Prozess festgelegt werden, auf die verwiesen wird von diesem `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="bca83-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="bca83-111">GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="bca83-112">Ruft einen Verweiszeiger auf dem angegebenen verwalteten Objekt, das eine Garbagecollection-handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="bca83-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="bca83-113">GetThreadForTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="bca83-114">Ruft den Thread, auf dem die Aufgabe mit dem angegebenen Bezeichner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bca83-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="bca83-115">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="bca83-116">Ruft die Version der CLR, auf denen der zu debuggende Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bca83-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="bca83-117">SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="bca83-118">Legt die Flags, die für den Just-in-Time (JIT)-Compiler, ein Bild in den zu debuggenden Prozess zu laden erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bca83-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="bca83-119">SetUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bca83-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="bca83-120">Legt einen Haltepunkt auf nicht verwalteten Offset angegebene systemeigene Image fest.</span><span class="sxs-lookup"><span data-stu-id="bca83-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bca83-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bca83-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bca83-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bca83-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bca83-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bca83-123">Requirements</span></span>  
 <span data-ttu-id="bca83-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bca83-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bca83-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bca83-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bca83-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bca83-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bca83-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bca83-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca83-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bca83-128">See Also</span></span>  
 [<span data-ttu-id="bca83-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bca83-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
