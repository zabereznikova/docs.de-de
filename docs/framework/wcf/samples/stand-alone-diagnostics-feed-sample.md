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
# <a name="stand-alone-diagnostics-feed-sample"></a>Feed-Beispiel
Dieses Beispiel demonstriert, wie Sie einen RSS-/ATOM-Feed für die Syndizierung mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erstellen. Es handelt sich um ein einfaches "Hello World"-Programm, das die Grundlagen des Objektmodells und die Einrichtung in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst zeigt.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modelliert Syndication-Feeds als Dienstoperationen, die einen speziellen Datentyp zurückgeben: <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Instanzen von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> können einen Feed sowohl in das Format RSS 2.0 als auch in das Format Atom 1.0 serialisieren. Der folgende Beispielcode zeigt den verwendeten Vertrag.  
  
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
  
 An die `GetProcesses`-Operation wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angehängt, das Ihnen ermöglicht zu steuern, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP GET-Anforderungen an Dienstoperationen verteilt werden, und das Format der gesendeten Nachrichten anzugeben.  
  
 Wie alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können Syndication-Feeds lokal oder in jeder verwalteten Anwendung selbst gehostet werden. Syndication-Dienste erfordern eine bestimmte Bindung (die <xref:System.ServiceModel.WebHttpBinding>) und ein bestimmtes Endpunktverhalten (das <xref:System.ServiceModel.Description.WebHttpBehavior>), um ordnungsgemäß zu funktionieren. Die neue <xref:System.ServiceModel.Web.WebServiceHost>-Klasse stellt eine geeignete API zur Erstellung solcher Endpunkte ohne eine spezielle Konfiguration bereit.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 Alternativ können Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> in einer in IIS gehosteten .svc-Datei verwenden, um die entsprechende Funktionalität bereitzustellen (dieses Verfahren wird in diesem Beispielcode nicht gezeigt).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Da dieser Dienst Anforderungen über die HTTP GET-Standardmethode empfängt, können Sie jeden beliebigen RSS- oder ATOM-fähigen Client verwenden, um auf den Dienst zuzugreifen. Sie können zum Beispiel die Ausgabe dieses Dienstes anzeigen, indem Sie mit einem RSS-fähigen Browser wie Internet Explorer&#160;7 nach http://localhost:8000/diagnostics/feed/?format=atom/ oder http://localhost:8000/diagnostics/feed/?format=rss navigieren.  
  
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
  
4.  Während die Konsolenanwendung ausgeführt wird, navigieren Sie mit einem RSS-fähigen Browser zu http://localhost:8000/diagnostics/feed/?format=atom oder http://localhost:8000/diagnostics/feed/?format=rss.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
