---
title: Verwenden der WCF-Entwicklungstools
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e315c9e77eace9bdb0e66abed203452e5d7f9bb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="f53ae-102">Verwenden der WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="f53ae-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="f53ae-103">In diesem Abschnitt wird beschrieben, die Visual Studio-Entwicklungstools, die Ihnen, bei der Entwicklung helfen können Ihrer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]Dienst.</span><span class="sxs-lookup"><span data-stu-id="f53ae-103">This section describes the Visual Studio development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="f53ae-104">Sie können die Visual Studio-Vorlagen als Grundlage verwenden, schnell einen eigenen Dienst zu erstellen, dann verwenden Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Auto-Host und [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client testen, Debuggen und Testen des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f53ae-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="f53ae-105">Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f53ae-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="f53ae-106">Die WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="f53ae-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="f53ae-107">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f53ae-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="f53ae-108">Sie können die vordefinierten Visual Studio Projekt- und Elementvorlagen in Visual Studio verwenden, beim schnellen Erstellen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste und entsprechende Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f53ae-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="f53ae-109">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="f53ae-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="f53ae-110">Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Auto-Host (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um zu hosten und automatisch einen implementierten Dienst zu testen.</span><span class="sxs-lookup"><span data-stu-id="f53ae-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="f53ae-111">Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f53ae-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="f53ae-112">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="f53ae-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="f53ae-113">Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="f53ae-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="f53ae-114">Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host ermöglicht er einen problemlosen Diensttest.</span><span class="sxs-lookup"><span data-stu-id="f53ae-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="f53ae-115">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="f53ae-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="f53ae-116">XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f53ae-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="f53ae-117">Die in den Daten definierten Klassen werden in Codetypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f53ae-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="f53ae-118">Verwenden der Tools ohne Administratorberechtigung</span><span class="sxs-lookup"><span data-stu-id="f53ae-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="f53ae-119">So aktivieren Sie die Benutzer ohne Administratorberechtigung entwickeln [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienste eine ACL (Access Control List) wird erstellt, für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f53ae-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="f53ae-120">Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f53ae-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="f53ae-121">Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="f53ae-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="f53ae-122">Darüber hinaus haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f53ae-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="f53ae-123">Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern.</span><span class="sxs-lookup"><span data-stu-id="f53ae-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="f53ae-124">Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:</span><span class="sxs-lookup"><span data-stu-id="f53ae-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f53ae-125"> Netsh.exe, finden Sie unter [wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="f53ae-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53ae-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53ae-126">See Also</span></span>  
 [<span data-ttu-id="f53ae-127">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f53ae-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="f53ae-128">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="f53ae-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="f53ae-129">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="f53ae-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
