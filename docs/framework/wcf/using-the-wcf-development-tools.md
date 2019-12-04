---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 59913f4c00c32699d788e2a0244798fc652361be
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802408"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="72b1f-102">Verwenden der WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="72b1f-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="72b1f-103">In diesem Abschnitt werden die Visual Studio-Entwicklungs Tools beschrieben, die Ihnen bei der Entwicklung von WCFService helfen können.</span><span class="sxs-lookup"><span data-stu-id="72b1f-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="72b1f-104">Sie können die Visual Studio-Vorlagen als Grundlage verwenden, um schnell einen eigenen Dienst zu erstellen, und dann den automatischen WCF-Dienst Host und den WCF-Test Client zum Debuggen und Testen des Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="72b1f-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="72b1f-105">Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="72b1f-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
 
 > [!NOTE]
 > <span data-ttu-id="72b1f-106">Ab Visual Studio 2017 werden die WCF-Entwicklungs Tools nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="72b1f-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="72b1f-107">Um diese Features zu verwenden, müssen Sie sicherstellen, dass die Windows Communication Foundation Komponente im Visual Studio-Installer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="72b1f-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="72b1f-108">Die WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="72b1f-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="72b1f-109">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72b1f-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="72b1f-110">Sie können die vordefinierten Visual Studio-Projekt-und-Element Vorlagen in Visual Studio verwenden, um schnell WCF-Dienste und umgebende Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72b1f-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="72b1f-111">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="72b1f-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="72b1f-112">Mit dem automatischen WCF-Dienst Host (WcfSvcHost. exe) können Sie den Visual Studio-Debugger (F5) starten, um automatisch einen von Ihnen implementierten Dienst zu hosten und zu testen.</span><span class="sxs-lookup"><span data-stu-id="72b1f-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="72b1f-113">Anschließend können Sie den Dienst mit dem WCF-Test Client (WcfTestClient. exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu finden und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="72b1f-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="72b1f-114">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="72b1f-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="72b1f-115">Der WCF-Test Client (WcfTestClient. exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die Antwort anzeigen können, die der Dienst zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="72b1f-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="72b1f-116">Diese Funktion bietet eine nahtlose Dienst Testfunktion, wenn Sie mit dem automatischen WCF-Dienst Host kombiniert wird.</span><span class="sxs-lookup"><span data-stu-id="72b1f-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="72b1f-117">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="72b1f-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="72b1f-118">XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="72b1f-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="72b1f-119">Die in den Daten definierten Klassen werden in Codetypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="72b1f-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="72b1f-120">Verwenden der Tools ohne Administratorberechtigung</span><span class="sxs-lookup"><span data-stu-id="72b1f-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="72b1f-121">Um Benutzern ohne Administratorrechte die Entwicklung von WCF-Diensten zu ermöglichen, wird während der Installation von Visual Studio eine ACL (Access Control Liste) für den Namespace "http://+:8731/Design_Time_Addresses" erstellt.</span><span class="sxs-lookup"><span data-stu-id="72b1f-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="72b1f-122">Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="72b1f-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="72b1f-123">Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="72b1f-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="72b1f-124">Außerdem können Benutzer den automatischen WCF-Dienst-Host (WcfSvcHost. exe) verwenden, ohne Ihnen Administratorrechte zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="72b1f-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="72b1f-125">Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern.</span><span class="sxs-lookup"><span data-stu-id="72b1f-125">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="72b1f-126">Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:</span><span class="sxs-lookup"><span data-stu-id="72b1f-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="72b1f-127">Weitere Informationen zu "Netsh. exe" finden [Sie unter Verwenden des Tools "Netsh. exe" und Befehls Zeilenschalter](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="72b1f-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b1f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72b1f-128">See also</span></span>

- [<span data-ttu-id="72b1f-129">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72b1f-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="72b1f-130">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="72b1f-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="72b1f-131">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="72b1f-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
