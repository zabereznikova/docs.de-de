---
title: 'Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 94d362767b92799fa54f46e71724284a92b5bf7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358820"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="28521-102">Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen</span><span class="sxs-lookup"><span data-stu-id="28521-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="28521-103">Führen Sie in einer teilweise vertrauenswürdigen Sicherheits-Sandbox, die auf das Internet Zone Berechtigungssatz beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="28521-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="28521-104">Dieser Berechtigungssatz beschränkt Webdienstaufrufe nur Webdienste, die sich auf befinden die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Ursprungssite der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="28521-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="28521-105">Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debuggt wird von Visual Studio 2005, allerdings gilt dies nicht als Standort für die gleichen Ursprungs wie der Webdienst, das sie verweisen.</span><span class="sxs-lookup"><span data-stu-id="28521-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="28521-106">Dieser bewirkt, dass Ausnahmen zur Codezugriffssicherheit ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="28521-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="28521-107">Allerdings eine Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projekt kann konfiguriert werden, um zu simulieren, müssen die gleiche Ursprungssite wie der Webdienst während des Debuggens ruft.</span><span class="sxs-lookup"><span data-stu-id="28521-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="28521-108">Dadurch wird die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] zu sicher Aufrufen des Webdiensts ohne Sicherheitsausnahmen.</span><span class="sxs-lookup"><span data-stu-id="28521-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="28521-109">Konfigurieren von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="28521-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="28521-110">So konfigurieren Sie Visual Studio 2005 zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die einen Webdienst aufruft:</span><span class="sxs-lookup"><span data-stu-id="28521-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1.  <span data-ttu-id="28521-111">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="28521-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="28521-112">In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="28521-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="28521-113">In der **Startaktion** wählen Sie im Abschnitt **externes Programm starten** , und geben Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="28521-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  <span data-ttu-id="28521-114">In der **Startoptionen** Geben Sie Folgendes in die **Befehlszeilenargumente** Textfeld:</span><span class="sxs-lookup"><span data-stu-id="28521-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="28521-115">`-debug`  *Dateiname*</span><span class="sxs-lookup"><span data-stu-id="28521-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="28521-116">Die *Filename* Wert für die **-Debuggen** -Parameter ist der XBAP-Dateiname, z. B.:</span><span class="sxs-lookup"><span data-stu-id="28521-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="28521-117">Dies ist die Standardkonfiguration für Lösungen, die mit dem Visual Studio 2005 erstellten [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="28521-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1.  <span data-ttu-id="28521-118">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="28521-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="28521-119">In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="28521-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="28521-120">In der **Startoptionen** Abschnitt, fügen Sie die folgende Befehlszeilenparameter ein, um die **Befehlszeilenargumente** Textfeld:</span><span class="sxs-lookup"><span data-stu-id="28521-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="28521-121">`-debugSecurityZoneURL` *URL*</span><span class="sxs-lookup"><span data-stu-id="28521-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="28521-122">Die *URL* Wert für die **- DebugSecurityZoneURL** -Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort an, die Sie als der Ursprungssite der Anwendung simulieren möchten.</span><span class="sxs-lookup"><span data-stu-id="28521-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="28521-123">Betrachten Sie beispielsweise eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , die einen Webdienst verwendet, durch den folgenden [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="28521-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="28521-124">Der Ursprungssite [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] für dieses Web-Dienst ist:</span><span class="sxs-lookup"><span data-stu-id="28521-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="28521-125">Daher ist die vollständige **- DebugSecurityZoneURL** Befehlszeilenparameter und der Wert ist:</span><span class="sxs-lookup"><span data-stu-id="28521-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="28521-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28521-126">See also</span></span>
- [<span data-ttu-id="28521-127">WPF-Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="28521-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
