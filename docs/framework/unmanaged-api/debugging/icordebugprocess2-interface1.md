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
ms.openlocfilehash: f1a30c197373928ec10c2b84de4e805b94ea2384
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724506"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="bd439-102">ICorDebugProcess2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd439-102">ICorDebugProcess2 Interface</span></span>

<span data-ttu-id="bd439-103">Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die einen Prozess darstellt, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="bd439-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd439-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bd439-104">Methods</span></span>  
  
|<span data-ttu-id="bd439-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-105">Method</span></span>|<span data-ttu-id="bd439-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd439-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd439-107">ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-107">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="bd439-108">Entfernt einen Haltepunkt am angegebenen Offset, der durch einen früheren-Aufrufsatz festgelegt wurde `ICorDebugProcess2::SetUnmanagedBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="bd439-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="bd439-109">GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-109">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="bd439-110">Ruft die Flags ab, die für die Common Language Runtime (CLR) festgelegt werden müssen, um das Bild in den Prozess zu laden, auf den von verwiesen wird `ICorDebugProcess2` .</span><span class="sxs-lookup"><span data-stu-id="bd439-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="bd439-111">GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-111">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="bd439-112">Ruft einen Verweis Zeiger auf das angegebene verwaltete Objekt ab, das über ein Garbage Collection Handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="bd439-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="bd439-113">GetThreadForTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-113">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="bd439-114">Ruft den Thread ab, in dem die Aufgabe mit dem angegebenen Bezeichner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd439-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="bd439-115">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-115">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="bd439-116">Ruft die Version der CLR ab, auf der der Prozess ausgeführt wird, der debuggt wird.</span><span class="sxs-lookup"><span data-stu-id="bd439-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="bd439-117">SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-117">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="bd439-118">Legt die Flags fest, die für den Just-in-time (JIT)-Compiler erforderlich sind, um ein Bild in den Prozess zu laden, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="bd439-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="bd439-119">SetUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bd439-119">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="bd439-120">Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Abbild Offset fest.</span><span class="sxs-lookup"><span data-stu-id="bd439-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd439-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd439-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd439-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bd439-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd439-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bd439-123">Requirements</span></span>  

 <span data-ttu-id="bd439-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd439-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd439-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd439-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd439-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd439-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd439-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd439-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd439-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd439-128">See also</span></span>

- [<span data-ttu-id="bd439-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd439-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
