---
title: Feed-Beispiel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c95a2e1e1790633df77e7c4ecd6603e68321e478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="01c3d-102">Feed-Beispiel</span><span class="sxs-lookup"><span data-stu-id="01c3d-102">Stand-Alone Diagnostics Feed Sample</span></span>
<span data-ttu-id="01c3d-103">Dieses Beispiel demonstriert, wie Sie einen RSS-/ATOM-Feed für die Syndizierung mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="01c3d-103">This sample demonstrates how to create an RSS/Atom feed for syndication with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="01c3d-104">Es handelt sich um ein einfaches "Hello World"-Programm, das die Grundlagen des Objektmodells und die Einrichtung in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst zeigt.</span><span class="sxs-lookup"><span data-stu-id="01c3d-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="01c3d-105"> modelliert Syndication-Feeds als Dienstoperationen, die einen speziellen Datentyp zurückgeben: <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="01c3d-105"> models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="01c3d-106">Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren.</span><span class="sxs-lookup"><span data-stu-id="01c3d-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="01c3d-107">Der folgende Beispielcode zeigt den verwendeten Vertrag.</span><span class="sxs-lookup"><span data-stu-id="01c3d-107">The following sample code shows the contract used.</span></span>  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 <span data-ttu-id="01c3d-108">An die `GetProcesses`-Operation wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angehängt, das Ihnen ermöglicht zu steuern, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP GET-Anforderungen an Dienstoperationen verteilt werden, und das Format der gesendeten Nachrichten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="01c3d-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="01c3d-109">Wie alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können Syndication-Feeds lokal oder in jeder verwalteten Anwendung selbst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="01c3d-109">Like any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="01c3d-110">Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="01c3d-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="01c3d-111">Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.</span><span class="sxs-lookup"><span data-stu-id="01c3d-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="01c3d-112">Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).</span><span class="sxs-lookup"><span data-stu-id="01c3d-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 <span data-ttu-id="01c3d-113">Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="01c3d-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="01c3d-114">Sie können zum Beispiel die Ausgabe dieses Dienstes anzeigen, indem Sie mit einem RSS-fähigen Browser wie Internet Explorer&#160;7 nach http://localhost:8000/diagnostics/feed/?format=atom/ oder http://localhost:8000/diagnostics/feed/?format=rss navigieren.</span><span class="sxs-lookup"><span data-stu-id="01c3d-114">For example, you can view the output of this service by navigating to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss in an RSS-aware browser such as Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="01c3d-115">Sie können auch die [wie das WCF Syndication-Objekt Modell Maps Atom und RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) syndizierte Daten gelesen und mithilfe von imperativem Code zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01c3d-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="01c3d-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="01c3d-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="01c3d-117">Stellen Sie sicher, dass Sie die richtige Adresse Registrierung-Berechtigung für HTTP und HTTPS auf dem Computer verfügen, wie in der Gruppe von Anweisungen in erläutert [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="01c3d-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="01c3d-118">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="01c3d-118">Build the solution.</span></span>  
  
3.  <span data-ttu-id="01c3d-119">Führen Sie die Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="01c3d-119">Run the console application.</span></span>  
  
4.  <span data-ttu-id="01c3d-120">Während die Konsolenanwendung ausgeführt wird, navigieren Sie mit einem RSS-fähigen Browser zu http://localhost:8000/diagnostics/feed/?format=atom oder http://localhost:8000/diagnostics/feed/?format=rss.</span><span class="sxs-lookup"><span data-stu-id="01c3d-120">While the console application is running, navigate to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss using an RSS-aware browser.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01c3d-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="01c3d-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="01c3d-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="01c3d-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01c3d-123">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="01c3d-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01c3d-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="01c3d-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a><span data-ttu-id="01c3d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01c3d-125">See Also</span></span>  
 [<span data-ttu-id="01c3d-126">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="01c3d-126">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="01c3d-127">WCF Syndication</span><span class="sxs-lookup"><span data-stu-id="01c3d-127">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
