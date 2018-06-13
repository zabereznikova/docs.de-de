---
title: Silverlight-Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80cee666a05432099a380a5ac547a5ca28698c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436032"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="01135-102">Silverlight-Debugging</span><span class="sxs-lookup"><span data-stu-id="01135-102">Silverlight Debugging</span></span>
<span data-ttu-id="01135-103">In den Themen dieses Abschnitts sind die Umgebung und die Schnittstellen beschrieben, mit denen die Common Language Runtime (CLR) das Debuggen von Silverlight-basierten Anwendungen unterstützt, die unter Windows oder auf der Macintosh-Plattform ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01135-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01135-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="01135-104">In This Section</span></span>  
 [<span data-ttu-id="01135-105">EnumerateCLRs-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="01135-106">Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="01135-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="01135-107">CloseCLREnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="01135-108">Schließt alle gültigen CLR-Starts weiterhin Ereignisse, die befindet sich in einem Array von Handles zurückgegebenes der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), und der Speicher für die Handle- und Pfadarrays freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="01135-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="01135-109">CreateCoreClrDebugTarget-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="01135-110">Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="01135-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="01135-111">CreateCordbObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="01135-112">Erstellt eine Debugschnittstelle, die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="01135-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="01135-113">CreateVersionStringFromModule-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="01135-114">Erstellt eine Versionszeichenfolge aus einem CLR-Pfad in einem Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="01135-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="01135-115">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="01135-116">Akzeptiert eine Versionszeichenfolge der CLR Merry [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)-Funktion und gibt eine entsprechende Debuggerschnittstelle zurück.</span><span class="sxs-lookup"><span data-stu-id="01135-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="01135-117">CoreClrDebugProcInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="01135-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="01135-118">Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01135-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="01135-119">CoreClrDebugRuntimeInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="01135-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="01135-120">Stellt eine CLR-Instanz dar, die in einem Prozess auf einem Remotecomputer geladen ist.</span><span class="sxs-lookup"><span data-stu-id="01135-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="01135-121">GetStartupNotificationEvent-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="01135-122">Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="01135-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="01135-123">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01135-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="01135-124">Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="01135-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="01135-125">InitDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="01135-126">Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="01135-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="01135-127">ShutdownDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="01135-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="01135-128">Fährt den Transport-Manager für eine Verbindung mit einem Remotecomputer herunter.</span><span class="sxs-lookup"><span data-stu-id="01135-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01135-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01135-129">See Also</span></span>  
 [<span data-ttu-id="01135-130">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="01135-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [<span data-ttu-id="01135-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01135-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="01135-132">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="01135-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [<span data-ttu-id="01135-133">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="01135-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="01135-134">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="01135-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
