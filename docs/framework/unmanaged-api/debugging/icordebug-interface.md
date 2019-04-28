---
title: ICorDebug-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786333"
---
# <a name="icordebug-interface"></a><span data-ttu-id="780a3-102">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="780a3-102">ICorDebug Interface</span></span>
<span data-ttu-id="780a3-103">Bietet Methoden, mit die Entwickler Anwendungen in der common Language Runtime (CLR)-Umgebung debuggen können.</span><span class="sxs-lookup"><span data-stu-id="780a3-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="780a3-104">Debuggen im gemischten Modus (verwalteter und systemeigener Code) wird auf Windows 95, Windows 98 oder Windows ME oder auf nicht-X86-Plattformen (z. B. IA64 und AMD64) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="780a3-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="780a3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="780a3-105">Methods</span></span>  
  
|<span data-ttu-id="780a3-106">Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-106">Method</span></span>|<span data-ttu-id="780a3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780a3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="780a3-108">CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="780a3-109">Bestimmt, ob ein neuer Prozess gestartet oder das Anfügen an den Prozess innerhalb des Kontexts der aktuellen Computer und -Runtime-Konfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="780a3-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="780a3-110">CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="780a3-111">Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="780a3-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="780a3-112">DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="780a3-113">Wird der Debugger an einen vorhandenen Prozess angefügt.</span><span class="sxs-lookup"><span data-stu-id="780a3-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="780a3-114">EnumerateProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="780a3-115">Ruft einen Enumerator für die Prozesse, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="780a3-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="780a3-116">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="780a3-117">Gibt das Objekt "ICorDebugProcess" mit dem angegebenen Prozess-ID zurück</span><span class="sxs-lookup"><span data-stu-id="780a3-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="780a3-118">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="780a3-119">Initialisiert das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="780a3-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="780a3-120">SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="780a3-121">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="780a3-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="780a3-122">SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="780a3-123">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="780a3-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="780a3-124">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="780a3-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="780a3-125">Beendet die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="780a3-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="780a3-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="780a3-126">Remarks</span></span>  
 <span data-ttu-id="780a3-127">`ICorDebug` Stellt ein Ereignisverarbeitungsschleife für einen Debuggerprozess dar.</span><span class="sxs-lookup"><span data-stu-id="780a3-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="780a3-128">Der Debugger muss warten, für die [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf von allen Prozessen, die vor dem Freigeben von dieser Schnittstelle gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="780a3-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="780a3-129">Die `ICorDebug` Objekt ist das ursprüngliche Objekt zum Steuern der gesamte Weitere Debuggen.</span><span class="sxs-lookup"><span data-stu-id="780a3-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="780a3-130">In der .NET Framework-Versionen 1.0 und 1.1, dieses Objekt wurde ein `CoClass` erstellte aus COM-Objekt</span><span class="sxs-lookup"><span data-stu-id="780a3-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="780a3-131">In .NET Framework, Version 2.0, ist dieses Objekt nicht mehr eine `CoClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="780a3-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="780a3-132">Es muss erstellt werden, indem die [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) -Funktion, die mehr Version-fähig ist.</span><span class="sxs-lookup"><span data-stu-id="780a3-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="780a3-133">Diese neue Funktion ermöglicht Clients das Abrufen einer bestimmten Implementierung der `ICorDebug`, die auch emuliert einer bestimmten Version von der Debug-API.</span><span class="sxs-lookup"><span data-stu-id="780a3-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="780a3-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="780a3-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780a3-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="780a3-135">Requirements</span></span>  
 <span data-ttu-id="780a3-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="780a3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780a3-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="780a3-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="780a3-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="780a3-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="780a3-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780a3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780a3-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="780a3-140">See also</span></span>

- [<span data-ttu-id="780a3-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="780a3-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
