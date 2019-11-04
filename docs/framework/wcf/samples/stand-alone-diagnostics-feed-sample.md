---
title: Feed-Beispiel
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: c8a64c209711734b4915f332e9242346e295ddea
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417041"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Feed-Beispiel
In diesem Beispiel wird veranschaulicht, wie ein RSS/Atom-Feed für die Syndizierung mit Windows Communication Foundation (WCF) erstellt wird. Dabei handelt es sich um ein einfaches "Hallo Welt"-Programm, das die Grundlagen des Objektmodells und die Einrichtung in einem Windows Communication Foundation (WCF)-Dienst anzeigt.  
  
 WCF modelliert Syndizierungs Feeds als Dienst Vorgänge, die einen speziellen Datentyp zurückgeben, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren. Der folgende Beispielcode zeigt den verwendeten Vertrag.  
  
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
  
 Der `GetProcesses` Vorgang wird mit dem <xref:System.ServiceModel.Web.WebGetAttribute> Attribut versehen, mit dem Sie steuern können, wie WCF HTTP GET-Anforderungen an Dienst Vorgänge sendet, und das Format der gesendeten Nachrichten angeben.  
  
 Ebenso wie alle WCF-Dienste können Syndizierungs Feeds in jeder verwalteten Anwendung selbst gehostet werden. Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren. Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen. Beispielsweise können Sie die Ausgabe dieses diensdienstanbieter anzeigen, indem Sie in einem RSS-fähigen Browser zu `http://localhost:8000/diagnostics/feed/?format=atom` oder `http://localhost:8000/diagnostics/feed/?format=rss` navigieren.
  
 Sie können auch die Art [und Weise verwenden, wie das WCF-Syndizierungs-Objektmodell Atom und RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) zuordnet, um syndizierte Daten zu lesen und mit imperativem Code zu verarbeiten.  
  
```csharp  
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
  
1. Stellen Sie sicher, dass Sie auf dem Computer über die Berechtigung zur Registrierung der richtigen Adresse für http und HTTPS verfügen, wie im Abschnitt Einrichten von Anweisungen in der [einmaligen Installation für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)erläutert.  
  
2. Erstellen Sie die Projektmappe.  
  
3. Führen Sie die Konsolenanwendung aus.  
  
4. Wenn die Konsolenanwendung ausgeführt wird, navigieren Sie zu `http://localhost:8000/diagnostics/feed/?format=atom` oder `http://localhost:8000/diagnostics/feed/?format=rss` mithilfe eines RSS-fähigen Browsers.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
