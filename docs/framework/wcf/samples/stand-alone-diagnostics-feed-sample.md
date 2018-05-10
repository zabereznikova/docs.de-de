---
title: Feed-Beispiel
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 730cf011208ea1b57929fff4a1953fd3a935335c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Feed-Beispiel
Dieses Beispiel veranschaulicht, wie einen RSS/Atom-feed für die Syndizierung mit Windows Communication Foundation (WCF) zu erstellen. Es ist eine einfache "Hello World"-Programm, das veranschaulicht die Grundlagen des Objektmodells und zum Einrichten eines Windows Communication Foundation (WCF)-Diensts.  
  
 WCF modelliert Syndication-Feeds als Dienstvorgänge, die einen speziellen Datentyp zurückgeben <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren. Der folgende Beispielcode zeigt den verwendeten Vertrag.  
  
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
  
 Die `GetProcesses` Vorgang mit dem versehen ist die <xref:System.ServiceModel.Web.WebGetAttribute> -Attribut, das können Sie steuern, wie WCF leitet HTTP GET-Anforderungen Dienstvorgänge, und geben Sie das Format der gesendeten Nachrichten.  
  
 Wie alle WCF-Dienst können Syndication-Feeds selbst in jeder verwalteten Anwendung gehostet werden. Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren. Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen. Sie können z. B. die Ausgabe dieses Dienstes anzeigen, navigieren Sie zur http://localhost:8000/diagnostics/feed/?format=atom oder http://localhost:8000/diagnostics/feed/?format=rss in einem RSS-fähigen Browser wie Internet Explorer 7.  
  
 Sie können auch die [wie das WCF Syndication-Objekt Modell Maps Atom und RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) syndizierte Daten gelesen und mithilfe von imperativem Code zu verarbeiten.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die richtige Adresse Registrierung-Berechtigung für HTTP und HTTPS auf dem Computer verfügen, wie in der Gruppe von Anweisungen in erläutert [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe.  
  
3.  Führen Sie die Konsolenanwendung aus.  
  
4.  Während die Konsolenanwendung ausgeführt wird, wechseln Sie zu http://localhost:8000/diagnostics/feed/?format=atom oder http://localhost:8000/diagnostics/feed/?format=rss mit einem RSS-fähigen Browser.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
