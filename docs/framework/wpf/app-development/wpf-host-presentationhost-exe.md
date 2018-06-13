---
title: WPF-Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: ca8198e17bec62866b6a58e6fd14ea468308f48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552687"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="44036-102">WPF-Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="44036-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="44036-103">Windows Presentation Foundation (WPF)-Host (PresentationHost.exe) ist die Anwendung, die es ermöglicht [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen in kompatiblen Browser gehostet werden (einschließlich [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] und höher).</span><span class="sxs-lookup"><span data-stu-id="44036-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="44036-104">Standardmäßig wird Windows Presentation Foundation (WPF)-Host als Shell registriert und [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] Handler für im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Inhalt, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="44036-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="44036-105">Loose (nicht kompilierte) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien (.xaml)</span><span class="sxs-lookup"><span data-stu-id="44036-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="44036-106"> (.xbap)</span><span class="sxs-lookup"><span data-stu-id="44036-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="44036-107">Für diese Dateitypen, Windows Presentation Foundation (WPF)-Host:</span><span class="sxs-lookup"><span data-stu-id="44036-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
-   <span data-ttu-id="44036-108">Startet den registrierten [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Handler zum Hosten des Inhalts von Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="44036-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
-   <span data-ttu-id="44036-109">Lädt die korrekten Versionen der erforderlichen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] und Windows Presentation Foundation (WPF)-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="44036-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
-   <span data-ttu-id="44036-110">Überprüfen, ob die entsprechenden Berechtigungsstufen für die Bereitstellungszone aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="44036-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="44036-111">In diesem Thema werden die Befehlszeilenparameter beschrieben, die mit „PresentationHost.exe“ verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="44036-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="44036-112">Verwendung</span><span class="sxs-lookup"><span data-stu-id="44036-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="44036-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="44036-113">Parameters</span></span>  
  
|<span data-ttu-id="44036-114">Parameter</span><span class="sxs-lookup"><span data-stu-id="44036-114">Parameter</span></span>|<span data-ttu-id="44036-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44036-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44036-116">filename</span><span class="sxs-lookup"><span data-stu-id="44036-116">filename</span></span>|<span data-ttu-id="44036-117">Der Pfad der zu aktivierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="44036-117">The path of the file to be activated.</span></span> <span data-ttu-id="44036-118">Es kann sich auch um einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] handeln.</span><span class="sxs-lookup"><span data-stu-id="44036-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="44036-119">-Debug</span><span class="sxs-lookup"><span data-stu-id="44036-119">-debug</span></span>|<span data-ttu-id="44036-120">Beim Aktivieren einer Anwendung wird diese nicht in den Speicher übernommen oder daraus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="44036-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="44036-121">Dies funktioniert nur, wenn eine lokale Datei aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="44036-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="44036-122">-debugSecurityZoneURL \<URL></span><span class="sxs-lookup"><span data-stu-id="44036-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="44036-123">Wird mit einem [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]-Wert verwendet, um für „PresentationHost.exe“ anzugeben, dass eine Anwendung so gedebuggt werden sollte, als ob sie von der angegebenen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] bereitgestellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="44036-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="44036-124">Dadurch werden die Bereitstellungszone und die Ursprungssite bestimmt.</span><span class="sxs-lookup"><span data-stu-id="44036-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="44036-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="44036-125">-embedding</span></span>|<span data-ttu-id="44036-126">Wird von OLE benötigt.</span><span class="sxs-lookup"><span data-stu-id="44036-126">Required by OLE.</span></span> <span data-ttu-id="44036-127">Wenn der Parameter `-event` oder `-debug` angegeben wird, ist es nicht nötig, den `-embedding`-Parameter anzugeben, da dieser Parameter intern festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="44036-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="44036-128">-event \<Ereignisname></span><span class="sxs-lookup"><span data-stu-id="44036-128">-event \<eventname></span></span>|<span data-ttu-id="44036-129">Öffnen Sie das Ereignis mit diesem Namen, und signalisieren Sie es, wenn „PresentationHost.exe“ initialisiert wird und bereit ist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Inhalte zu hosten.</span><span class="sxs-lookup"><span data-stu-id="44036-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="44036-130">„PresentationHost.exe“ wird beendet, wenn beim Öffnen des Ereignisses ein Fehler auftritt, z. B. wenn es noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="44036-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="44036-131">-launchApplication \<URL></span><span class="sxs-lookup"><span data-stu-id="44036-131">-launchApplication \<url></span></span>|<span data-ttu-id="44036-132">Startet eine eigenständige [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Anwendung unter Verwendung der angegebenen URL.</span><span class="sxs-lookup"><span data-stu-id="44036-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]<span data-ttu-id="44036-133">- und WinInet-Sicherheitsrichtlinie für .NET-Anwendungen werden angewendet.</span><span class="sxs-lookup"><span data-stu-id="44036-133"> and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="44036-134">Szenarien</span><span class="sxs-lookup"><span data-stu-id="44036-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="44036-135">Shell-Handler</span><span class="sxs-lookup"><span data-stu-id="44036-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="44036-136">MIME-Handler</span><span class="sxs-lookup"><span data-stu-id="44036-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="44036-137">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44036-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="44036-138">Visual Studio: Debuggen in einer Zone</span><span class="sxs-lookup"><span data-stu-id="44036-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="44036-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44036-139">See Also</span></span>  
 [<span data-ttu-id="44036-140">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="44036-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
