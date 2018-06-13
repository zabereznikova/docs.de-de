---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 52b908d354771cb2b351e339881647462340b716
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806525"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="08678-102">SystemWebRouting-Integrationsbeispiel</span><span class="sxs-lookup"><span data-stu-id="08678-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="08678-103">In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="08678-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="08678-104">Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="08678-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="08678-105">Webrouting ermöglicht dem Entwickler, Erstellen von virtuellen Adressen für HTTP, die dann wieder an die tatsächlichen WCF-Dienste zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="08678-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="08678-106">Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten.</span><span class="sxs-lookup"><span data-stu-id="08678-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="08678-107">In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="08678-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="08678-108">Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="08678-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="08678-109">In diesem Beispiel verwendet die WCF zum Erstellen von zwei RSS-Feeds: ein `movies` feed und ein `channels` feed.</span><span class="sxs-lookup"><span data-stu-id="08678-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="08678-110">Die URLs zur Aktivierung der Dienste enthalten keine Erweiterung und registriert sind, der `Application_Start` Methode der `Global` abgeleitete Klasse die <xref:System.Web.HttpApplication> Klasse.</span><span class="sxs-lookup"><span data-stu-id="08678-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08678-111">Dieses Beispiel funktioniert nur in Internetinformationsdienste (IIS) 7.0 und höher, wie IIS 6.0 verwendet eine andere Methode für die Unterstützung von URLs ohne Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="08678-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="08678-112">Dieses Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="08678-112">To download this sample</span></span>
  
<span data-ttu-id="08678-113">In diesem Beispiel möglicherweise bereits auf Ihrem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="08678-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="08678-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="08678-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="08678-115">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="08678-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="08678-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="08678-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="08678-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="08678-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="08678-118">Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="08678-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="08678-119">Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.</span><span class="sxs-lookup"><span data-stu-id="08678-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="08678-120">Eine Verzeichnisliste für das Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08678-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="08678-121">Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.</span><span class="sxs-lookup"><span data-stu-id="08678-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="08678-122">Fügen Sie in der Adressleiste `movies` an die URL so, dass die It liest http://localhost:[Port] / Movies und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="08678-122">In the address bar, add `movies` to the URL, so that it reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="08678-123">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08678-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="08678-124">Fügen Sie in der Adressleiste `channels` an die URL, also Lesevorgänge http://localhost:[Port] / channels lautet, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="08678-124">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="08678-125">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08678-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="08678-126">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="08678-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="08678-127">Wenn der Entwicklungsserver nicht beendet wurde, mit der rechten Maustaste das Symbol im Infobereich, und wählen Sie **beenden**.</span><span class="sxs-lookup"><span data-stu-id="08678-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="08678-128">So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird</span><span class="sxs-lookup"><span data-stu-id="08678-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="08678-129">Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="08678-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="08678-130">Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="08678-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="08678-131">Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.</span><span class="sxs-lookup"><span data-stu-id="08678-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="08678-132">Mit der rechten Maustaste im IIS-Manager, klicken Sie auf die **Default Web Site** , und wählen Sie **Hinzufügen einer Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="08678-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="08678-133">Für die **Alias**, geben Sie in `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="08678-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="08678-134">Für die **physischen Pfad**, wählen Sie den Dienstordner im Projekt.</span><span class="sxs-lookup"><span data-stu-id="08678-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="08678-135">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="08678-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="08678-136">Starten Sie die Anwendung, indem Sie die Web-Anwendung mit der rechten Maustaste und auswählen **-Anwendung verwalten** und dann **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="08678-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="08678-137">Fügen Sie in der Adressleiste `movies` an die URL, also Lesevorgänge http://localhost:[Port] / Movies und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="08678-137">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="08678-138">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08678-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="08678-139">Fügen Sie in der Adressleiste `channels` an die URL, also Lesevorgänge http://localhost:[Port] / channels lautet, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="08678-139">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="08678-140">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08678-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="08678-141">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="08678-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="08678-142">In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="08678-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08678-143">Sie müssen die Version des Standardanwendungspools auf Aktualisieren [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] , wenn sie auf Version 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="08678-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08678-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08678-144">See Also</span></span>  
 [<span data-ttu-id="08678-145">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="08678-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
