---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: e9a398ac6914582d299658e3e45d17ea5468917d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712089"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="afce6-102">Verwenden der WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="afce6-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="afce6-103">Dieser Abschnitt beschreibt die Visual Studio-Entwicklungstools, die Sie bei der Entwicklung von Entwicklungswerkzeuge unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="afce6-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="afce6-104">Sie können Visual Studio-Vorlagen als Grundlage verwenden, um einen eigenen Dienst schnell zu erstellen und dann die WCF-Dienst-Auto-Host und WCF-Testclient zum Debuggen und Testen des Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="afce6-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="afce6-105">Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="afce6-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="afce6-106">Die WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="afce6-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="afce6-107">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="afce6-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="afce6-108">Sie können die vordefinierten Visual Studio Projekt- und Elementvorlagen in Visual Studio verwenden, um WCF-Dienste und entsprechende Anwendungen schnell erstellen.</span><span class="sxs-lookup"><span data-stu-id="afce6-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="afce6-109">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="afce6-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="afce6-110">Der WCF-Dienst-Auto-Host (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um automatisch zu hosten und Testen einen Dienst, den Sie implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="afce6-110">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="afce6-111">Anschließend können Sie den Dienst mit den WCF-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client zum Suchen und beheben potenzielle Fehler testen.</span><span class="sxs-lookup"><span data-stu-id="afce6-111">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="afce6-112">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="afce6-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="afce6-113">WCF-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, übermitteln, die Eingabe an den Dienst und die zurückgesendete Anzeigen der Antwort des Diensts.</span><span class="sxs-lookup"><span data-stu-id="afce6-113">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="afce6-114">Es bietet eine nahtlose diensttest in Kombination mit WCF-Dienst-Auto-Host.</span><span class="sxs-lookup"><span data-stu-id="afce6-114">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="afce6-115">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="afce6-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="afce6-116">XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="afce6-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="afce6-117">Die in den Daten definierten Klassen werden in Codetypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="afce6-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="afce6-118">Verwenden der Tools ohne Administratorberechtigung</span><span class="sxs-lookup"><span data-stu-id="afce6-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="afce6-119">Um Benutzer ohne Administratorrechte zum Entwickeln von WCF-Dienste zu aktivieren, wird eine ACL (Access Control List) erstellt, für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="afce6-119">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="afce6-120">Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="afce6-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="afce6-121">Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="afce6-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="afce6-122">Sie können auch Benutzer die WCF-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne ihnen Administratorrechte zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="afce6-122">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="afce6-123">Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern.</span><span class="sxs-lookup"><span data-stu-id="afce6-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="afce6-124">Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:</span><span class="sxs-lookup"><span data-stu-id="afce6-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="afce6-125">Weitere Informationen zu Netsh.exe, finden Sie unter [wie mit dem Netsh.exe-Tool und die Befehlszeilenoptionen](https://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="afce6-125">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afce6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afce6-126">See also</span></span>
- [<span data-ttu-id="afce6-127">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="afce6-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)
- [<span data-ttu-id="afce6-128">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="afce6-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="afce6-129">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="afce6-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
