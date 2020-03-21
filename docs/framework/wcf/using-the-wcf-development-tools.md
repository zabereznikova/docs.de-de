---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183078"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="9cfe9-102">Verwenden der WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="9cfe9-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="9cfe9-103">In diesem Abschnitt werden die Visual Studio-Entwicklungstools beschrieben, die Sie bei der Entwicklung Ihres WCFservice unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="9cfe9-104">Sie können die Visual Studio-Vorlagen als Grundlage verwenden, um schnell Ihren eigenen Dienst zu erstellen, und dann WCF Service Auto Host und WCF Test Client verwenden, um Ihren Dienst zu debuggen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="9cfe9-105">Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="9cfe9-106">Ab Visual Studio 2017 werden die WCF-Entwicklungstools standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="9cfe9-107">Um diese Features verwenden zu können, müssen Sie sicherstellen, dass die Windows Communication Foundation-Komponente im Visual Studio-Installationsprogramm ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="9cfe9-108">Die WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="9cfe9-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="9cfe9-109">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9cfe9-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="9cfe9-110">Sie können die vordefinierten Visual Studio-Projekt- und Elementvorlagen in Visual Studio verwenden, um WCF-Dienste und umgebende Anwendungen schnell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="9cfe9-111">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9cfe9-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="9cfe9-112">Mit dem WCF Service Auto Host (WcfSvcHost.exe) können Sie den Visual Studio-Debugger (F5) starten, um einen von Ihnen implementierten Dienst automatisch zu hosten und zu testen.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="9cfe9-113">Anschließend können Sie den Dienst mit dem WCF-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um mögliche Fehler zu finden und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="9cfe9-114">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9cfe9-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="9cfe9-115">WCF Test Client (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, diese Eingabe an den Dienst übermitteln und die Antwort anzeigen können, die der Dienst zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="9cfe9-116">In Kombination mit WCF Service Auto Host bietet es eine nahtlose Servicetestumgebung.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="9cfe9-117">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="9cfe9-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="9cfe9-118">XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="9cfe9-119">Die in den Daten definierten Klassen werden in Codetypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="9cfe9-120">Verwenden der Tools ohne Administratorberechtigung</span><span class="sxs-lookup"><span data-stu-id="9cfe9-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="9cfe9-121">Um Benutzern ohne Administratorberechtigung das Entwickeln von WCF-Diensten zu ermöglichen, wirdhttp://+:8731/Design_Time_Addresseswährend der Installation von Visual Studio eine ACL (Access Control List) für den Namespace " erstellt.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="9cfe9-122">Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="9cfe9-123">Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="9cfe9-124">Außerdem können Benutzer den WCF Service Auto Host (wcfSvcHost.exe) verwenden, ohne ihnen Administratorrechte zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="9cfe9-125">Sie können den Zugriff mit dem Tool Netsh.exe in Windows Vista unter dem erweiterten Administratorkonto ändern.</span><span class="sxs-lookup"><span data-stu-id="9cfe9-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="9cfe9-126">Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:</span><span class="sxs-lookup"><span data-stu-id="9cfe9-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="9cfe9-127">Weitere Informationen zu Netsh.exe finden Sie unter [Verwenden des Netsh.exe-Tools und der Befehlszeilenschalter](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="9cfe9-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfe9-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cfe9-128">See also</span></span>

- [<span data-ttu-id="9cfe9-129">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9cfe9-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="9cfe9-130">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9cfe9-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="9cfe9-131">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9cfe9-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
