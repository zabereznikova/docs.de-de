---
title: Silverlight-Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 49f026b8e1a3dd78a62091e77a5aba0c9a2e09d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671836"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="34538-102">Silverlight-Debugging</span><span class="sxs-lookup"><span data-stu-id="34538-102">Silverlight Debugging</span></span>

<span data-ttu-id="34538-103">In den Themen dieses Abschnitts sind die Umgebung und die Schnittstellen beschrieben, mit denen die Common Language Runtime (CLR) das Debuggen von Silverlight-basierten Anwendungen unterstützt, die unter Windows oder auf der Macintosh-Plattform ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34538-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34538-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="34538-104">In This Section</span></span>  

 [<span data-ttu-id="34538-105">EnumerateCLRs-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-105">EnumerateCLRs Function</span></span>](enumerateclrs-function.md)  
 <span data-ttu-id="34538-106">Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="34538-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="34538-107">CloseCLREnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-107">CloseCLREnumeration Function</span></span>](closeclrenumeration-function.md)  
 <span data-ttu-id="34538-108">Schließt alle gültigen CLR-Continue-Startup-Ereignisse in einem Array von Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden, und gibt den Arbeitsspeicher für die Array-und Zeichen folgen Pfad Arrays frei.</span><span class="sxs-lookup"><span data-stu-id="34538-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="34538-109">CreateCoreClrDebugTarget-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-109">CreateCoreClrDebugTarget Function</span></span>](createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="34538-110">Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="34538-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="34538-111">CreateCordbObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-111">CreateCordbObject Function</span></span>](createcordbobject-function.md)  
 <span data-ttu-id="34538-112">Erstellt eine Debugschnittstelle, die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="34538-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="34538-113">CreateVersionStringFromModule-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-113">CreateVersionStringFromModule Function</span></span>](createversionstringfrommodule-function.md)  
 <span data-ttu-id="34538-114">Erstellt eine Versionszeichenfolge aus einem CLR-Pfad in einem Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="34538-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="34538-115">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-115">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="34538-116">Akzeptiert eine CLR-Versions Zeichenfolge, die von der Funktion "die Funktion" der Funktion "" der Funktion "" der [Funktion "Funktion](createversionstringfrommodule-function.md)" zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="34538-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="34538-117">CoreClrDebugProcInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="34538-117">CoreClrDebugProcInfo Structure</span></span>](coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="34538-118">Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34538-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="34538-119">CoreClrDebugRuntimeInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="34538-119">CoreClrDebugRuntimeInfo Structure</span></span>](coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="34538-120">Stellt eine CLR-Instanz dar, die in einem Prozess auf einem Remotecomputer geladen ist.</span><span class="sxs-lookup"><span data-stu-id="34538-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="34538-121">GetStartupNotificationEvent-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-121">GetStartupNotificationEvent Function</span></span>](getstartupnotificationevent-function.md)  
 <span data-ttu-id="34538-122">Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="34538-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="34538-123">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34538-123">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="34538-124">Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="34538-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="34538-125">InitDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-125">InitDbgTransportManager Function</span></span>](initdbgtransportmanager-function.md)  
 <span data-ttu-id="34538-126">Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="34538-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="34538-127">ShutdownDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="34538-127">ShutdownDbgTransportManager Function</span></span>](shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="34538-128">Fährt den Transport-Manager für eine Verbindung mit einem Remotecomputer herunter.</span><span class="sxs-lookup"><span data-stu-id="34538-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34538-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34538-129">See also</span></span>

- [<span data-ttu-id="34538-130">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="34538-130">Debugging Coclasses</span></span>](debugging-coclasses.md)
- [<span data-ttu-id="34538-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="34538-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="34538-132">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="34538-132">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
- [<span data-ttu-id="34538-133">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="34538-133">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="34538-134">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="34538-134">Debugging Structures</span></span>](debugging-structures.md)
