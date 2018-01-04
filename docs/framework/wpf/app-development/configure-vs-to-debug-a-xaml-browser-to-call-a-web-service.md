---
title: 'Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 330ee213e147cfef709c919c95cb0e58159bc37b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="42148-102">Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen</span><span class="sxs-lookup"><span data-stu-id="42148-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="42148-103">Führen Sie in einem Sandkasten Sicherheit bei teilweiser Vertrauenswürdigkeit, die auf das Internet Zone Berechtigungssatz beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="42148-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="42148-104">Dieser Berechtigungssatz beschränkt Webdienstaufrufe, die nur auf Webdienste, die unter der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Ursprungssite der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="42148-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="42148-105">Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aus gedebuggt wird [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], obwohl er nicht die gleiche Ursprungssite haben, wie im Web service Verweise betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="42148-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="42148-106">Diese Ursachen Sicherheitsausnahmen ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="42148-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="42148-107">Allerdings eine [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projekt kann konfiguriert werden, um zu simulieren, die gleiche Ursprungssite wie der Webdienst aufgerufen wird, während des Debuggens.</span><span class="sxs-lookup"><span data-stu-id="42148-107">However, a [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="42148-108">Dies ermöglicht die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] problemlos den Webdienst aufrufen, ohne Sicherheitsausnahmen.</span><span class="sxs-lookup"><span data-stu-id="42148-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>  
  
## <a name="configuring-visual-studio"></a><span data-ttu-id="42148-109">Konfigurieren von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42148-109">Configuring Visual Studio</span></span>  
 <span data-ttu-id="42148-110">So konfigurieren Sie [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] einen Webdienst aufruft:</span><span class="sxs-lookup"><span data-stu-id="42148-110">To configure [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>  
  
1.  <span data-ttu-id="42148-111">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="42148-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="42148-112">In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="42148-112">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="42148-113">In der **Startaktion** Abschnitt **externes Programm starten** und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="42148-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  <span data-ttu-id="42148-114">In der **Startoptionen** Abschnitt, geben Sie Folgendes in die **Befehlszeilenargumente** Textfeld:</span><span class="sxs-lookup"><span data-stu-id="42148-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="42148-115">`-debug`  *Dateiname*</span><span class="sxs-lookup"><span data-stu-id="42148-115">`-debug`  *filename*</span></span>  
  
     <span data-ttu-id="42148-116">Die *Filename* Wert für die **-Debuggen** Parameter ist der XBAP-Dateiname, z. B.:</span><span class="sxs-lookup"><span data-stu-id="42148-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  <span data-ttu-id="42148-117">Dies ist die Standardkonfiguration für Projektmappen, die mit erstellt wurden, die [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] -Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="42148-117">This is the default configuration for solutions that are created with the [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>  
  
1.  <span data-ttu-id="42148-118">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="42148-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="42148-119">In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="42148-119">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="42148-120">In der **Startoptionen** Abschnitt, fügen Sie die folgenden Befehlszeilenparameter, die **Befehlszeilenargumente** Textfeld:</span><span class="sxs-lookup"><span data-stu-id="42148-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="42148-121">`-debugSecurityZoneURL` *URL*</span><span class="sxs-lookup"><span data-stu-id="42148-121">`-debugSecurityZoneURL`  *URL*</span></span>  
  
     <span data-ttu-id="42148-122">Die *URL* Wert für die **- DebugSecurityZoneURL** Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort, den Sie als der Ursprungssite Ihrer Anwendung simulieren möchten.</span><span class="sxs-lookup"><span data-stu-id="42148-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>  
  
 <span data-ttu-id="42148-123">Betrachten Sie als Beispiel eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] verwendet, die einen Webdienst mit den folgenden [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="42148-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 <span data-ttu-id="42148-124">Der Ursprungssite [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] für diese Web-Dienst ist:</span><span class="sxs-lookup"><span data-stu-id="42148-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>  
  
 `http://services.msdn.microsoft.com`  
  
 <span data-ttu-id="42148-125">Infolgedessen ist die vollständige **- DebugSecurityZoneURL** Befehlszeilenparameter und Wert ist:</span><span class="sxs-lookup"><span data-stu-id="42148-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a><span data-ttu-id="42148-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42148-126">See Also</span></span>  
 [<span data-ttu-id="42148-127">WPF-Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="42148-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
