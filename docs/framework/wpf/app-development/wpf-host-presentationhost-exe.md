---
title: WPF-Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: ec8ec42c174d87834af5d4c651c1e8c8bde3b3e2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581700"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="9433b-102">WPF-Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9433b-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="9433b-103">Windows Presentation Foundation (WPF)-Host (PresentationHost. exe) ist die Anwendung, mit der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen in kompatiblen Browsern (einschließlich Microsoft Internet Explorer 6 und höher) gehostet werden können.</span><span class="sxs-lookup"><span data-stu-id="9433b-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="9433b-104">Standardmäßig wird der WPF-Host (Windows Presentation Foundation) als Shell und MIME-Handler für im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Inhalt registriert, der Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="9433b-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="9433b-105">Loose (nicht kompilierte) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien (.xaml)</span><span class="sxs-lookup"><span data-stu-id="9433b-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="9433b-106">(.xbap)</span><span class="sxs-lookup"><span data-stu-id="9433b-106">(.xbap).</span></span>  
  
 <span data-ttu-id="9433b-107">Für Dateien dieser Typen Windows Presentation Foundation (WPF)-Host:</span><span class="sxs-lookup"><span data-stu-id="9433b-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="9433b-108">Hiermit wird der registrierte HTML-Handler zum Hosten des Windows Presentation Foundation-Inhalts (WPF) gestartet.</span><span class="sxs-lookup"><span data-stu-id="9433b-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="9433b-109">Lädt die richtigen Versionen der erforderlichen Common Language Runtime-Assemblys (CLR) und Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9433b-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="9433b-110">Überprüfen, ob die entsprechenden Berechtigungsstufen für die Bereitstellungszone aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="9433b-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="9433b-111">In diesem Thema werden die Befehlszeilenparameter beschrieben, die mit „PresentationHost.exe“ verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9433b-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="9433b-112">Verwendung</span><span class="sxs-lookup"><span data-stu-id="9433b-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="9433b-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="9433b-113">Parameters</span></span>  
  
|<span data-ttu-id="9433b-114">Parameter</span><span class="sxs-lookup"><span data-stu-id="9433b-114">Parameter</span></span>|<span data-ttu-id="9433b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9433b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9433b-116">filename</span><span class="sxs-lookup"><span data-stu-id="9433b-116">filename</span></span>|<span data-ttu-id="9433b-117">Der Pfad der zu aktivierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="9433b-117">The path of the file to be activated.</span></span> <span data-ttu-id="9433b-118">Kann auch ein URI sein.</span><span class="sxs-lookup"><span data-stu-id="9433b-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="9433b-119">-Debug</span><span class="sxs-lookup"><span data-stu-id="9433b-119">-debug</span></span>|<span data-ttu-id="9433b-120">Beim Aktivieren einer Anwendung wird diese nicht in den Speicher übernommen oder daraus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9433b-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="9433b-121">Dies funktioniert nur, wenn eine lokale Datei aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9433b-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="9433b-122">-debugSecurityZoneURL \<URL></span><span class="sxs-lookup"><span data-stu-id="9433b-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="9433b-123">Wird mit einem URL-Wert verwendet, um PresentationHost. exe anzugeben, dass eine Anwendung deentschlbelt werden soll, als ob Sie von der angegebenen URL bereitgestellt würde.</span><span class="sxs-lookup"><span data-stu-id="9433b-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="9433b-124">Dadurch werden die Bereitstellungszone und die Ursprungssite bestimmt.</span><span class="sxs-lookup"><span data-stu-id="9433b-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="9433b-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="9433b-125">-embedding</span></span>|<span data-ttu-id="9433b-126">Wird von OLE benötigt.</span><span class="sxs-lookup"><span data-stu-id="9433b-126">Required by OLE.</span></span> <span data-ttu-id="9433b-127">Wenn der Parameter `-event` oder `-debug` angegeben wird, ist es nicht nötig, den `-embedding`-Parameter anzugeben, da dieser Parameter intern festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9433b-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="9433b-128">-event \<Ereignisname></span><span class="sxs-lookup"><span data-stu-id="9433b-128">-event \<eventname></span></span>|<span data-ttu-id="9433b-129">Öffnen Sie das Ereignis mit diesem Namen, und signalisieren Sie es, wenn „PresentationHost.exe“ initialisiert wird und bereit ist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Inhalte zu hosten.</span><span class="sxs-lookup"><span data-stu-id="9433b-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="9433b-130">„PresentationHost.exe“ wird beendet, wenn beim Öffnen des Ereignisses ein Fehler auftritt, z. B. wenn es noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9433b-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="9433b-131">-launchApplication \<URL></span><span class="sxs-lookup"><span data-stu-id="9433b-131">-launchApplication \<url></span></span>|<span data-ttu-id="9433b-132">Hiermit wird eine eigenständige ClickOnce-Anwendung aus der angegebenen URL gestartet.</span><span class="sxs-lookup"><span data-stu-id="9433b-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="9433b-133">Internet Explorer und WinInet-Sicherheitsrichtlinie für .NET-Anwendungen werden angewendet.</span><span class="sxs-lookup"><span data-stu-id="9433b-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="9433b-134">Szenarien</span><span class="sxs-lookup"><span data-stu-id="9433b-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="9433b-135">Shell-Handler</span><span class="sxs-lookup"><span data-stu-id="9433b-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="9433b-136">MIME-Handler</span><span class="sxs-lookup"><span data-stu-id="9433b-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="9433b-137">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9433b-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="9433b-138">Visual Studio: Debuggen in einer Zone</span><span class="sxs-lookup"><span data-stu-id="9433b-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="9433b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9433b-139">See also</span></span>

- [<span data-ttu-id="9433b-140">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9433b-140">Security</span></span>](../security-wpf.md)
