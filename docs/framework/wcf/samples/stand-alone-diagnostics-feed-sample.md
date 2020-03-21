---
title: Feed-Beispiel
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 29d8caee48925040db9f1812f015870e3a1272bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144005"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Feed-Beispiel
In diesem Beispiel wird veranschaulicht, wie Sie einen RSS/Atom-Feed für die Syndizierung mit Windows Communication Foundation (WCF) erstellen. Es ist ein grundlegendes "Hello World"-Programm, das die Grundlagen des Objektmodells und das Einrichten auf einem Windows Communication Foundation (WCF)-Dienst zeigt.  
  
 WCF-Modelle syndication feeds als Service-Vorgänge, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>die einen speziellen Datentyp zurückgeben, . Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren. Der folgende Beispielcode zeigt den verwendeten Vertrag.  
  
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
  
 Der `GetProcesses` Vorgang wird mit dem <xref:System.ServiceModel.Web.WebGetAttribute> Attribut mit Anmerkungen versehen, mit dem Sie steuern können, wie WCF HTTP GET-Anforderungen an Dienstvorgänge auslöst, und das Format der gesendeten Nachrichten angeben.  
  
 Wie bei jedem WCF-Dienst können Syndizierungsfeeds in jeder verwalteten Anwendung selbst gehostet werden. Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren. Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).  
  
```xml
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen. Sie können z. B. die Ausgabe dieses `http://localhost:8000/diagnostics/feed/?format=atom` `http://localhost:8000/diagnostics/feed/?format=rss` Dienstes anzeigen, indem Sie zu oder in einem RSS-basierten Browser navigieren.
  
 Sie können auch die [Verwendung des WCF Syndication Object Model Maps to Atom und RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) verwenden, um syndizierte Daten zu lesen und sie mithilfe von Imperative-Code zu verarbeiten.  
  
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
  
## <a name="set-up-build-and-run-the-sample"></a>Einrichten, Erstellen und Ausführen des Beispiels
  
1. Stellen Sie sicher, dass Sie über die richtige Adressregistrierungsberechtigung für HTTP und HTTPS auf dem Computer verfügen, wie in den Einrichtungsanweisungen im [einmaligen Setupverfahren für die Windows Communication Foundation-Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)erläutert.

2. Erstellen Sie die Projektmappe.

3. Führen Sie die Konsolenanwendung aus.

4. Navigieren Sie während der Ausführung `http://localhost:8000/diagnostics/feed/?format=atom` `http://localhost:8000/diagnostics/feed/?format=rss` der Konsolenanwendung zu einem RSS-basierten Browser oder mit diesem.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a>Weitere Informationen

- [WCF-Web-HTTP-Programmiermodell](../feature-details/wcf-web-http-programming-model.md)
- [WCF Syndication](../feature-details/wcf-syndication.md)
