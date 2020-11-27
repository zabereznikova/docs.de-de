---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 04c3093097c5bf11e1d4dd5d3124c9fbae4b3665
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293909"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="bf8da-102">SystemWebRouting-Integrationsbeispiel</span><span class="sxs-lookup"><span data-stu-id="bf8da-102">SystemWebRouting Integration Sample</span></span>

<span data-ttu-id="bf8da-103">In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bf8da-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="bf8da-104">Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bf8da-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="bf8da-105">Die Verwendung von Webrouting ermöglicht es dem Entwickler, virtuelle Adressen für http zu erstellen, die dann wieder den eigentlichen WCF-Diensten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8da-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="bf8da-106">Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten.</span><span class="sxs-lookup"><span data-stu-id="bf8da-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="bf8da-107">In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8da-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span>

> [!NOTE]
> <span data-ttu-id="bf8da-108">Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8da-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="bf8da-109">In diesem Beispiel werden WCF verwendet, um zwei RSS-Feeds zu erstellen: einen `movies` Feed und einen `channels` Feed.</span><span class="sxs-lookup"><span data-stu-id="bf8da-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="bf8da-110">Die URLs zum Aktivieren der Dienste enthalten keine Erweiterung und werden in der- `Application_Start` Methode der Klasse registriert, die `Global` von der- <xref:System.Web.HttpApplication> Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="bf8da-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf8da-111">Dieses Beispiel funktioniert nur in Internetinformationsdienste (IIS) 7,0 und höher, da IIS 6,0 eine andere Methode zur Unterstützung von URLs ohne Erweiterungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf8da-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="bf8da-112">So laden Sie dieses Beispiel herunter</span><span class="sxs-lookup"><span data-stu-id="bf8da-112">To download this sample</span></span>
  
<span data-ttu-id="bf8da-113">Dieses Beispiel ist möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="bf8da-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="bf8da-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="bf8da-114">Check for the following (default) directory before continuing.</span></span>  

`<InstallDrive>:\WF_WCF_Samples`  

 <span data-ttu-id="bf8da-115">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf8da-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bf8da-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bf8da-116">This sample is located in the following directory.</span></span>  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bf8da-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf8da-117">To use this sample</span></span>  
  
1. <span data-ttu-id="bf8da-118">Öffnen Sie in Visual Studio die Datei "webroutingintegration. sln".</span><span class="sxs-lookup"><span data-stu-id="bf8da-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="bf8da-119">Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.</span><span class="sxs-lookup"><span data-stu-id="bf8da-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="bf8da-120">Eine Verzeichnisliste für das Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="bf8da-121">Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="bf8da-122">Fügen Sie in der Adressleiste `movies` die URL hinzu, damit Sie gelesen wird, `http://localhost:[port]/movies` und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bf8da-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="bf8da-123">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="bf8da-124">Fügen Sie in der Adressleiste `channels` der URL ein, sodass der Lese `http://localhost:[port]/channels` -und drücken der EINGABETASTE ist.</span><span class="sxs-lookup"><span data-stu-id="bf8da-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="bf8da-125">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="bf8da-126">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="bf8da-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="bf8da-127">Wenn der Entwicklungs Server nicht beendet wurde, klicken Sie mit der rechten Maustaste auf das Benachrichtigungs Bereichs Symbol, und wählen Sie **Beenden** aus.</span><span class="sxs-lookup"><span data-stu-id="bf8da-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="bf8da-128">So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird</span><span class="sxs-lookup"><span data-stu-id="bf8da-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="bf8da-129">Öffnen Sie in Visual Studio die Datei "webroutingintegration. sln".</span><span class="sxs-lookup"><span data-stu-id="bf8da-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="bf8da-130">Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="bf8da-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="bf8da-131">Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.</span><span class="sxs-lookup"><span data-stu-id="bf8da-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="bf8da-132">Klicken Sie im IIS-Manager mit der rechten Maustaste auf die **Standard Website** , und wählen Sie **Anwendung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="bf8da-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="bf8da-133">Geben Sie für den **Alias** ein `WebRoutingIntegration` .</span><span class="sxs-lookup"><span data-stu-id="bf8da-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="bf8da-134">Wählen Sie für den **physischen Pfad** den Dienst Ordner innerhalb des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="bf8da-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="bf8da-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf8da-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="bf8da-136">Starten Sie die Anwendung, indem Sie mit der rechten Maustaste auf die Webanwendung klicken und **Anwendung verwalten** und dann **Durchsuchen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="bf8da-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="bf8da-137">Fügen Sie in der Adressleiste `movies` der URL ein, sodass der Lese `http://localhost:[port]/movies` -und drücken der EINGABETASTE ist.</span><span class="sxs-lookup"><span data-stu-id="bf8da-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="bf8da-138">Der Filmfeed (movies) wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="bf8da-139">Fügen Sie in der Adressleiste `channels` der URL ein, sodass der Lese `http://localhost:[port]/channels` -und drücken der EINGABETASTE ist.</span><span class="sxs-lookup"><span data-stu-id="bf8da-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="bf8da-140">Der Channelfeed wird im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf8da-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="bf8da-141">Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.</span><span class="sxs-lookup"><span data-stu-id="bf8da-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="bf8da-142">In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8da-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf8da-143">Sie müssen die standardmäßige Anwendungs Poolversion auf .NET Framework 4 aktualisieren, wenn Sie auf Version 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bf8da-143">You must update the default application pool version to .NET Framework 4 if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf8da-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf8da-144">See also</span></span>

- <span data-ttu-id="bf8da-145">[AppFabric-Hosting- und -Persistenzbeispiele](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bf8da-145">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
