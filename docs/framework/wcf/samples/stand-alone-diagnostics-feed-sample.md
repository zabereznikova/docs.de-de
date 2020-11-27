---
title: Feed-Beispiel
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: b4c3613656e0aec42c0d3f5cd7cde0af6540a69a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268247"
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="1fe62-102">Feed-Beispiel</span><span class="sxs-lookup"><span data-stu-id="1fe62-102">Stand-Alone Diagnostics Feed Sample</span></span>

<span data-ttu-id="1fe62-103">In diesem Beispiel wird veranschaulicht, wie ein RSS/Atom-Feed für die Syndizierung mit Windows Communication Foundation (WCF) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1fe62-103">This sample demonstrates how to create an RSS/Atom feed for syndication with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1fe62-104">Dabei handelt es sich um ein einfaches "Hallo Welt"-Programm, das die Grundlagen des Objektmodells und die Einrichtung in einem Windows Communication Foundation (WCF)-Dienst anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1fe62-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="1fe62-105">WCF modelliert Syndizierungs Feeds als Dienst Vorgänge, die einen speziellen Datentyp zurückgeben <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> .</span><span class="sxs-lookup"><span data-stu-id="1fe62-105">WCF models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="1fe62-106">Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1fe62-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="1fe62-107">Der folgende Beispielcode zeigt den verwendeten Vertrag.</span><span class="sxs-lookup"><span data-stu-id="1fe62-107">The following sample code shows the contract used.</span></span>  
  
```csharp  
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
  
 <span data-ttu-id="1fe62-108">Der `GetProcesses` Vorgang wird mit dem-Attribut kommentiert <xref:System.ServiceModel.Web.WebGetAttribute> , mit dem Sie steuern können, wie WCF HTTP GET-Anforderungen an Dienst Vorgänge sendet, und das Format der gesendeten Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="1fe62-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how WCF dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="1fe62-109">Ebenso wie alle WCF-Dienste können Syndizierungs Feeds in jeder verwalteten Anwendung selbst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1fe62-109">Like any WCF service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="1fe62-110">Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1fe62-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="1fe62-111">Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.</span><span class="sxs-lookup"><span data-stu-id="1fe62-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="1fe62-112">Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).</span><span class="sxs-lookup"><span data-stu-id="1fe62-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```xml
<% @ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 <span data-ttu-id="1fe62-113">Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1fe62-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="1fe62-114">Beispielsweise können Sie die Ausgabe dieses Dienstanbieter anzeigen, indem Sie zu `http://localhost:8000/diagnostics/feed/?format=atom` oder `http://localhost:8000/diagnostics/feed/?format=rss` in einem RSS-fähigen Browser navigieren.</span><span class="sxs-lookup"><span data-stu-id="1fe62-114">For example, you can view the output of this service by navigating to `http://localhost:8000/diagnostics/feed/?format=atom` or `http://localhost:8000/diagnostics/feed/?format=rss` in an RSS-aware browser.</span></span>
  
 <span data-ttu-id="1fe62-115">Sie können auch die Art [und Weise verwenden, wie das WCF-Syndizierungs-Objektmodell Atom und RSS](../feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) zuordnet, um syndizierte Daten zu lesen und mit imperativem Code zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1fe62-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```csharp
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",
    new XmlReaderSettings()
    {
        //MaxCharactersInDocument can be used to control the maximum amount of data
        //read from the reader and helps prevent OutOfMemoryException
        MaxCharactersInDocument = 1024 * 64
    } );

SyndicationFeed feed = SyndicationFeed.Load(reader);

foreach (SyndicationItem i in feed.Items)
{
    XmlSyndicationContent content = i.Content as XmlSyndicationContent;
    ProcessData pd = content.ReadContent<ProcessData>();

    Console.WriteLine(i.Title.Text);
    Console.WriteLine(pd.ToString());
}
```
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="1fe62-116">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1fe62-116">Set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="1fe62-117">Stellen Sie sicher, dass Sie auf dem Computer über die Berechtigung zur Registrierung der richtigen Adresse für http und HTTPS verfügen, wie im Abschnitt Einrichten von Anweisungen in der [einmaligen Installation für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="1fe62-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1fe62-118">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="1fe62-118">Build the solution.</span></span>

3. <span data-ttu-id="1fe62-119">Führen Sie die Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="1fe62-119">Run the console application.</span></span>

4. <span data-ttu-id="1fe62-120">Während die Konsolenanwendung ausgeführt wird, navigieren Sie zu `http://localhost:8000/diagnostics/feed/?format=atom` oder `http://localhost:8000/diagnostics/feed/?format=rss` über einen RSS-fähigen Browser.</span><span class="sxs-lookup"><span data-stu-id="1fe62-120">While the console application is running, navigate to `http://localhost:8000/diagnostics/feed/?format=atom` or `http://localhost:8000/diagnostics/feed/?format=rss` using an RSS-aware browser.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fe62-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1fe62-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1fe62-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1fe62-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1fe62-123">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1fe62-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1fe62-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1fe62-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a><span data-ttu-id="1fe62-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fe62-125">See also</span></span>

- [<span data-ttu-id="1fe62-126">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="1fe62-126">WCF Web HTTP Programming Model</span></span>](../feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="1fe62-127">WCF Syndication</span><span class="sxs-lookup"><span data-stu-id="1fe62-127">WCF Syndication</span></span>](../feature-details/wcf-syndication.md)
