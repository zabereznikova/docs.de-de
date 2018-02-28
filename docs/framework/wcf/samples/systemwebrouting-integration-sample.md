---
title: SystemWebRouting-Integrationsbeispiel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de8869956a59cb47623dbc4d84763e19d6f181bf
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="5fb2c-102">SystemWebRouting-Integrationsbeispiel</span><span class="sxs-lookup"><span data-stu-id="5fb2c-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="5fb2c-103">In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="5fb2c-104">Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="5fb2c-105">Webrouting ermöglicht es dem Entwickler, virtuelle Adressen für HTTP zu erstellen, die danach erneut tatsächlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="5fb2c-106">Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="5fb2c-107">In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="5fb2c-108">Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="5fb2c-109">In diesem Beispiel verwendet die WCF zum Erstellen von zwei RSS-Feeds: ein `movies` feed und ein `channels` feed.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="5fb2c-110">Die URLs zur Aktivierung der Dienste enthalten keine Erweiterung und registriert sind, der `Application_Start` Methode der `Global` abgeleitete Klasse die <xref:System.Web.HttpApplication> Klasse.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fb2c-111">Dieses Beispiel funktioniert nur in Internetinformationsdienste (IIS) 7.0 und höher, wie IIS 6.0 verwendet eine andere Methode für die Unterstützung von URLs ohne Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="5fb2c-112">Dieses Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="5fb2c-112">To download this sample</span></span>
  
<span data-ttu-id="5fb2c-113">In diesem Beispiel möglicherweise bereits auf Ihrem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="5fb2c-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="5fb2c-115">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5fb2c-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5fb2c-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fb2c-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="5fb2c-118">Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="5fb2c-119">Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="5fb2c-120">Eine Verzeichnisliste für das Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="5fb2c-121">Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="5fb2c-122">Fügen Sie in der Adressleiste `movies` an die URL, liest die It also http://localhost: [Port] / Movies und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-122">In the address bar, add `movies` to the URL, so that it reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="5fb2c-123">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="5fb2c-124">Fügen Sie der URL in der Adressleiste `channels` hinzu, sodass die Adresse nun http://localhost:[Port]/channels lautet, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-124">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="5fb2c-125">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="5fb2c-126">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="5fb2c-127">Wenn der Entwicklungsserver nicht beendet wurde, mit der rechten Maustaste das Symbol im Infobereich, und wählen Sie **beenden**.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="5fb2c-128">So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird</span><span class="sxs-lookup"><span data-stu-id="5fb2c-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="5fb2c-129">Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="5fb2c-130">Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5fb2c-131">Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="5fb2c-132">Mit der rechten Maustaste im IIS-Manager, klicken Sie auf die **Default Web Site** , und wählen Sie **Hinzufügen einer Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="5fb2c-133">Für die **Alias**, geben Sie in `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="5fb2c-134">Für die **physischen Pfad**, wählen Sie den Dienstordner im Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="5fb2c-135">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="5fb2c-136">Starten Sie die Anwendung, indem Sie die Web-Anwendung mit der rechten Maustaste und auswählen **-Anwendung verwalten** und dann **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="5fb2c-137">Fügen Sie der URL in der Adressleiste `movies` hinzu, sodass die Adresse nun http://localhost:[Port]/movies lautet, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-137">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="5fb2c-138">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="5fb2c-139">Fügen Sie der URL in der Adressleiste `channels` hinzu, sodass die Adresse nun http://localhost:[Port]/channels lautet, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-139">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="5fb2c-140">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="5fb2c-141">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="5fb2c-142">In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fb2c-143">Sie müssen die Version des Standardanwendungspools auf Aktualisieren [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] , wenn sie auf Version 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5fb2c-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb2c-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fb2c-144">See Also</span></span>  
 [<span data-ttu-id="5fb2c-145">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="5fb2c-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
