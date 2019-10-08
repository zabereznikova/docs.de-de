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
ms.openlocfilehash: 8ec278f2bc66d9b40786123af684f6468b6a9d83
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005671"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="223f3-102">Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen</span><span class="sxs-lookup"><span data-stu-id="223f3-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="223f3-103">wird in einer teilweise vertrauenswürdigen Sicherheits Sandbox ausgeführt, die auf den Berechtigungs Satz für die Internet Zone beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="223f3-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="223f3-104">Dieser Berechtigungs Satz schränkt Webdienst Aufrufe nur auf Webdienste ein, die sich auf der Ursprungs Site der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendung befinden.</span><span class="sxs-lookup"><span data-stu-id="223f3-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="223f3-105">Wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aus Visual Studio 2005 deentschlbelt wird, wird Sie nicht als dieselbe Ursprungs Site wie der Webdienst betrachtet, auf den Sie verweist.</span><span class="sxs-lookup"><span data-stu-id="223f3-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="223f3-106">Dies bewirkt, dass Sicherheits Ausnahmen ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="223f3-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="223f3-107">Ein Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]-Projekt kann jedoch so konfiguriert werden, dass es die gleiche Ursprungs Site wie der Webdienst simuliert, der beim Debuggen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="223f3-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="223f3-108">Dies ermöglicht es dem [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], den Webdienst sicher aufzurufen, ohne Sicherheits Ausnahmen zu verursachen.</span><span class="sxs-lookup"><span data-stu-id="223f3-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="223f3-109">Konfigurieren von Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="223f3-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="223f3-110">So konfigurieren Sie Visual Studio 2005 zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], die einen Webdienst aufruft:</span><span class="sxs-lookup"><span data-stu-id="223f3-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="223f3-111">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="223f3-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="223f3-112">Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .</span><span class="sxs-lookup"><span data-stu-id="223f3-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="223f3-113">Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="223f3-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="223f3-114">Geben Sie im Abschnitt **Start Optionen** Folgendes in das Textfeld **Befehlszeilenargumente** ein:</span><span class="sxs-lookup"><span data-stu-id="223f3-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="223f3-115">*Dateiname* von `-debug`</span><span class="sxs-lookup"><span data-stu-id="223f3-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="223f3-116">Der *Dateiname* des Parameters "-Debug" ist der **Dateiname** ". XBAP". Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="223f3-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="223f3-117">Dies ist die Standardkonfiguration für Projektmappen, die mit der Projektvorlage Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="223f3-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="223f3-118">Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="223f3-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="223f3-119">Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .</span><span class="sxs-lookup"><span data-stu-id="223f3-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="223f3-120">Fügen Sie im Abschnitt **Start Optionen** den folgenden Befehlszeilenparameter in das Textfeld **Befehlszeilenargumente** ein:</span><span class="sxs-lookup"><span data-stu-id="223f3-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="223f3-121">`-debugSecurityZoneURL` *URL*</span><span class="sxs-lookup"><span data-stu-id="223f3-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="223f3-122">Der *URL* -Wert für den **-DebugSecurityZoneURL-** Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort, den Sie als Ursprungs Site der Anwendung simulieren möchten.</span><span class="sxs-lookup"><span data-stu-id="223f3-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="223f3-123">Angenommen, ein [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] verwendet einen Webdienst mit der folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="223f3-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="223f3-124">Die URL für den Ursprungs Standort für diesen Webdienst lautet:</span><span class="sxs-lookup"><span data-stu-id="223f3-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="223f3-125">Folglich lautet der Befehlszeilenparameter Complete **-Debug securityzoneurl** und der Wert:</span><span class="sxs-lookup"><span data-stu-id="223f3-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="223f3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="223f3-126">See also</span></span>

- [<span data-ttu-id="223f3-127">WPF-Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="223f3-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
