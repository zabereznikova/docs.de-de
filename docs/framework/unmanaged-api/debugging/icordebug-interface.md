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
ms.openlocfilehash: 74c5036bdc8a4a75e5711c6dc1d34d8f2c21128f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408670"
---
# <a name="icordebug-interface"></a><span data-ttu-id="20312-102">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20312-102">ICorDebug Interface</span></span>
<span data-ttu-id="20312-103">Enthält Methoden, die Entwickler beim Debuggen von Anwendungen in der common Language Runtime (CLR)-Umgebung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="20312-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20312-104">Debuggen im gemischten Modus (verwalteter und systemeigener Code) wird unter Windows 95, Windows 98 oder Windows ME sowie auf nicht X86-Plattformen (z. B. IA64 und AMD64) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20312-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20312-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="20312-105">Methods</span></span>  
  
|<span data-ttu-id="20312-106">Methode</span><span class="sxs-lookup"><span data-stu-id="20312-106">Method</span></span>|<span data-ttu-id="20312-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20312-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20312-108">CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="20312-109">Bestimmt, ob ein neuer Prozess gestartet oder Anhängen an den angegebenen Prozess innerhalb des Kontexts der aktuellen Konfiguration für Computer und die Common Language Runtime möglich ist.</span><span class="sxs-lookup"><span data-stu-id="20312-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="20312-110">CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="20312-111">Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="20312-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="20312-112">DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="20312-113">Fügt der Debugger an einen vorhandenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="20312-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="20312-114">EnumerateProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="20312-115">Ruft einen Enumerator für die Prozesse, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="20312-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="20312-116">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="20312-117">Gibt das Objekt "ICorDebugProcess" mit der angegebenen Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="20312-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="20312-118">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="20312-119">Initialisiert die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="20312-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="20312-120">SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="20312-121">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="20312-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="20312-122">SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="20312-123">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="20312-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="20312-124">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="20312-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="20312-125">Beendet die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="20312-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20312-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20312-126">Remarks</span></span>  
 <span data-ttu-id="20312-127">`ICorDebug` Stellt ein Ereignisverarbeitungsschleife für keinen Debuggerprozess dar.</span><span class="sxs-lookup"><span data-stu-id="20312-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="20312-128">Der Debugger muss warten, für die [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf von allen Prozessen, die vor dem Freigeben von dieser Schnittstelle gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="20312-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="20312-129">Die `ICorDebug` Objekt ist das erste Objekt, das alle weiteren verwalteten Debuggens steuern.</span><span class="sxs-lookup"><span data-stu-id="20312-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="20312-130">In der .NET Framework-Versionen 1.0 und 1.1, dieses Objekt wurde ein `CoClass` erstellte aus COM-Objekt</span><span class="sxs-lookup"><span data-stu-id="20312-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="20312-131">In .NET Framework, Version 2.0, ist dieses Objekt nicht mehr eine `CoClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="20312-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="20312-132">Es muss erstellt werden, indem die [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) -Funktion, die mehr Version-fähig ist.</span><span class="sxs-lookup"><span data-stu-id="20312-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="20312-133">Diese neue Funktion ermöglicht Clients erhalten eine spezifische Implementierung `ICorDebug`, die auch eine bestimmte Version von der Debug-API emuliert.</span><span class="sxs-lookup"><span data-stu-id="20312-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20312-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="20312-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20312-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20312-135">Requirements</span></span>  
 <span data-ttu-id="20312-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20312-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20312-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20312-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20312-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20312-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20312-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20312-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20312-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20312-140">See Also</span></span>  
 [<span data-ttu-id="20312-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="20312-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
