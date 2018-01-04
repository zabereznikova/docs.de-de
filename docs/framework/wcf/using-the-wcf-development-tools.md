---
title: Verwenden der WCF-Entwicklungstools
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d253f38fab21496dd305cc67e7b6e84846579f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="e1782-102">Verwenden der WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="e1782-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="e1782-103">In diesem Abschnitt wird beschrieben, die [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Entwicklungstools, die Ihnen, bei der Entwicklung helfen können Ihrer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]Dienst.</span><span class="sxs-lookup"><span data-stu-id="e1782-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="e1782-104">Sie können die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Vorlagen als Grundlage verwenden, um schnell einen eigenen Dienst zu erstellen, verwenden Sie dann [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Auto-Host und [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client testen, Debuggen und Testen des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e1782-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="e1782-105">Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e1782-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="e1782-106">Die WCF-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="e1782-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="e1782-107">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e1782-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="e1782-108">Sie können die vordefinierten [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Projekt- und Elementvorlagen in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] schnell erstellen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste und entsprechende Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e1782-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="e1782-109">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e1782-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="e1782-110">Mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (WcfSvcHost.exe) können Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Debugger (F5) starten, um automatisch einen implementierten Dienst zu hosten und zu testen.</span><span class="sxs-lookup"><span data-stu-id="e1782-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="e1782-111">Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e1782-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="e1782-112">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="e1782-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="e1782-113">Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="e1782-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="e1782-114">Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host ermöglicht er einen problemlosen Diensttest.</span><span class="sxs-lookup"><span data-stu-id="e1782-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="e1782-115">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="e1782-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="e1782-116">XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1782-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="e1782-117">Die in den Daten definierten Klassen werden in Codetypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e1782-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="e1782-118">Verwenden der Tools ohne Administratorberechtigung</span><span class="sxs-lookup"><span data-stu-id="e1782-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="e1782-119">Damit auch Benutzer ohne Administratorberechtigung [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste entwickeln können, wird während der Installation von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eine ACL (Access Control List) für den Namespace "http://+:8731/Design_Time_Addresses" erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1782-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="e1782-120">Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e1782-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="e1782-121">Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="e1782-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="e1782-122">Darüber hinaus haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e1782-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="e1782-123">Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern.</span><span class="sxs-lookup"><span data-stu-id="e1782-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="e1782-124">Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:</span><span class="sxs-lookup"><span data-stu-id="e1782-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="e1782-125">Netsh.exe, finden Sie unter [wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="e1782-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1782-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1782-126">See Also</span></span>  
 [<span data-ttu-id="e1782-127">WCF Visual Studio-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e1782-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="e1782-128">WCF-Diensthost (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e1782-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="e1782-129">WCF-Testclient (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="e1782-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
