---
title: Erweiterte Filter
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a374765317751a5adc241941a0c0dc613a3ea2cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="advanced-filters"></a>Erweiterte Filter
In diesem Beispiel wird ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Routingdienst veranschaulicht. Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht. In diesem Beispiel wird das standardmäßige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst. In diesem Beispiel wird gezeigt, wie die inhaltsbasierte Routinglogik durch die Verwendung von Nachrichtenfiltern und Nachrichtenfiltertabellen definiert wird.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a>Beispieldetails  
 In der folgenden Tabelle werden die Nachrichtenfilter angezeigt, die der Nachrichtenfiltertabelle des Routingdiensts hinzugefügt werden.  
  
|Filter|Regel|Priorität|  
|------------|----------|--------------|  
|If (hat Header)|Runden|2|  
|If (angezeigt an Ep2)|Regulär|1|  
|If (angezeigt mit Address2)|Runden|1|  
|If (RoundRobin1)|Regulär|0|  
|If (RoundRobin2)|Runden|0|  
  
 Die Nachrichtenfilter und Nachrichtenfiltertabellen können entweder durch Code oder in der Anwendungskonfigurationsdatei erstellt und konfiguriert werden. Für dieses Beispiel finden Sie die durch Code definierten Nachrichtenfilter und Nachrichtenfiltertabellen in der Datei RoutingService\routing.cs bzw. die in der Anwendungskonfigurationsdatei definierten Nachrichtenfilter und Nachrichtenfiltertabellen in der Datei RoutingService\App.config. In den folgenden Absätzen wird beschrieben, wie die Nachrichtenfilter und Nachrichtenfiltertabellen für dieses Beispiel durch Code erstellt werden.  
  
 Zuerst sucht ein <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> nach dem benutzerdefinierten Header. Beachten Sie, dass <xref:System.ServiceModel.WSHttpBinding> zu einer Umschlagversion führt, die SOAP 1.2 verwendet, sodass die XPath-Anweisung für die Verwendung des SOAP 1.2-Namespace definiert wird. Der standardmäßige Namespace-Manager für <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> definiert bereits ein Präfix für den SOAP 1.2-Namespace, /s12, das verwendet werden kann. Der standardmäßige Namespace-Manager verfügt jedoch nicht über den benutzerdefinierten Namespace, mit dem der Client den tatsächlichen Headerwert definiert, sodass dieses Präfix definiert werden muss. Der Filter ergibt für jede Nachricht, die mit diesem Header angezeigt wird, eine Übereinstimmung.  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 Der zweite Filter ist ein <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, der für jede Nachricht eine Übereinstimmung ergibt, die am `calculatorEndpoint` empfangen wurde. Der Endpunktname wird definiert, wenn ein Dienstendpunktobjekt erstellt wird.  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 Der dritte Filter ist ein <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>. Dieser Filter ergibt für jede Nachricht eine Übereinstimmung, die an einem Endpunkt mit einer Adresse angezeigt wurde, die mit dem angegebenen Adresspräfix (oder dem Anfang) übereinstimmt. In diesem Beispiel wird das Adresspräfix als definiert "http://localhost/routingservice/router/rounding/". Dies bedeutet, dass alle eingehenden Nachrichten, die an adressiert sind "http://localhost/routingservice/router/rounding/*", die von diesem Filter abgeglichen werden. In diesem Fall ist es Nachrichten, die auf den rundungsrechnerendpunkt angezeigt werden, werden die hat der Adresse des "http://localhost/routingservice/router/rounding/calculator".  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 Die letzten beiden Nachrichtenfilter sind benutzerdefinierte <xref:System.ServiceModel.Dispatcher.MessageFilter>. In diesem Beispiel wird ein "RoundRobin"-Nachrichtenfilter verwendet. Dieser Nachrichtenfilter wird in der bereitgestellten Datei RoutingService\RoundRobinMessageFilter.cs erstellt. Wenn diese Filter für dieselbe Gruppe festgelegt werden, melden sie abwechselnd, dass sie mit der Nachricht übereinstimmen und dass sie nicht mit der Nachricht übereinstimmen, sodass zu jedem gegebenen Zeitpunkt nur ein Filter `true` zurückgibt.  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 Als Nächstes werden diese Nachrichten zu einer <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> hinzugefügt. Dadurch werden Prioritäten festgelegt, die die Reihenfolge beeinflussen, in der die Filter in der Nachrichtenfiltertabelle ausgeführt werden. Je höher die Priorität, desto früher wird der Filter ausgeführt; je niedriger die Priorität, desto später wird ein Filter ausgeführt. So wird ein Filter mit Priorität 2 vor einem Filter mit Priorität 1 ausgeführt. Wenn keine Priorität angegeben wird, wird die Standardprioritätsstufe 0 verwendet. In einer Nachrichtenfiltertabelle werden alle Filter einer bestimmten Prioritätsstufe ausgeführt, bevor zur nächst niedrigeren Prioritätsstufe übergegangen wird. Wenn eine Übereinstimmung gefunden wird, fährt die Nachrichtenfiltertabelle nicht auf der nächst niedrigeren Prioritätsstufe mit der Suche nach Übereinstimmungen fort.  
  
> [!NOTE]
>  In diesem Beispiel wird zwar die Verwendung von Nachrichtenfilterprioritäten gezeigt, im Allgemeinen empfiehlt es sich jedoch, die Filter so zu entwerfen und zu konfigurieren, dass sie keine Prioritäten benötigen, um ordnungsgemäß zu funktionieren, weil dadurch eine höhere Leistung und Anwendbarkeit erzielt wird.  
  
 Der erste hinzuzufügende Filter ist der XPath-Filter, und seine Priorität ist auf 2 festgelegt. Dies ist der erste Nachrichtenfilter, der ausgeführt wird. Wenn er den benutzerdefinierten Header findet, wird die Nachricht unabhängig von den möglichen Ergebnissen der anderen Filter an den Rundungsrechnerendpunkt weitergeleitet.  
  
 Zwei Filter werden mit Priorität 1 hinzugefügt. Diese werden wiederum nur ausgeführt, wenn der XPath-Filter mit Priorität 2 für die Nachricht keine Übereinstimmung ergibt. Diese beiden Filter zeigen zwei verschiedene Möglichkeiten, um zu bestimmen, wo die Nachricht adressiert wurde, als sie angezeigt wurde. Da die beiden Filter effektiv überprüfen, ob die Nachricht an einem der beiden Endpunkte eingegangen ist, können sie mit derselben Prioritätsstufe ausgeführt werden, da sie nicht beide gleichzeitig `true` zurückgegeben.  
  
 Führen Sie schließlich die RoundRobin-Nachrichtenfilter auf der Prioritätsstufe 0 (der niedrigsten Priorität) aus. Da die Filter mit demselben Gruppennamen konfiguriert sind, ergibt immer nur einer eine Übereinstimmung. Da alle Nachrichten mit dem benutzerdefinierten Header und alle Nachrichten, die an die bestimmten virtualisierten Endpunkte adressiert sind, weitergeleitet wurden, werden nur die Nachrichten von RoundRobin-Nachrichtenfiltern verarbeitet, die an den Standardrouterendpunkt ohne den benutzerdefinierten Header adressiert waren. Da für diese Nachrichten bei jedem Aufruf ein Wechsel stattfindet, wird die Hälfte der Vorgänge an den regulären Rechnerendpunkt und die andere Hälfte an den Rundungsrechnerendpunkt geleitet.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie AdvancedFilters.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  So öffnen **Projektmappen-Explorer**wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.  
  
3.  Drücken Sie F5 oder STRG + UMSCHALT + B in Visual Studio aus.  
  
    1.  Möchten Sie die notwendigen Projekte automatisch gestartet, wenn Sie F5 drücken, Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**. Wählen Sie die **Startprojekt** Knoten unter **allgemeine Eigenschaften** im linken Bereich. Wählen Sie die **mehrere Startprojekte** Optionsfeld aus, und legen Sie alle Projekte haben die **starten** Aktion.  
  
    2.  Wenn Sie das Projekt mit STRG+UMSCHALT+B erstellen, müssen Sie die folgenden Anwendungen starten:  
  
        1.  Rechnerclient (./CalculatorClient/bin/client.exe)  
  
        2.  Rechnerdienst (./CalculatorService/bin/service.exe)  
  
        3.  Routingrechnerdienst (./RoundingCalcService/bin/service.exe)  
  
        4.  Routingdienst (./RoutingService/bin/RoutingService.exe)  
  
4.  Drücken Sie im Konsolenfenster des Rechnerclients die EINGABETASTE, um den Client zu starten. Der Client gibt eine Liste mit Zielendpunkten zur Auswahl zurück.  
  
5.  Wählen Sie einen Zielendpunkt aus, indem Sie den entsprechenden Buchstaben eingeben und die EINGABETASTE drücken.  
  
6.  Als Nächstes fordert Sie der Client auf, einzugeben, ob ein benutzerdefinierter Header hinzugefügt werden soll. Drücken Sie Y für Ja oder N für Nein, und drücken Sie dann die EINGABETASTE.  
  
7.  Abhängig von der getroffenen Auswahl werden unterschiedliche Ausgaben angezeigt.  
  
    1.  Die folgende Ausgabe wird zurückgegeben, wenn Sie einen benutzerdefinierten Header zu den Nachrichten hinzugefügt haben.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  Die folgende Ausgabe wird zurückgegeben, wenn Sie den Rundungsrechnerendpunkt ohne benutzerdefinierten Header ausgewählt haben.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  Die folgende Ausgabe wird zurückgegeben, wenn Sie den regulären Rechnerendpunkt ohne benutzerdefinierten Header ausgewählt haben.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  Die folgende Ausgabe wird zurückgegeben, wenn Sie den Standardrouterendpunkt ohne benutzerdefinierten Header ausgewählt haben.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  Vom Rechnerdienst und Rundungsrechnerdienst wird außerdem ein Protokoll der Vorgänge gedruckt, die in den jeweiligen Konsolenfenstern aufgerufen werden.  
  
9. Geben Sie im Konsolenfenster Clients `quit` , und drücken Sie EINGABETASTE, um zu beenden.  
  
10. Drücken Sie die EINGABETASTE in den Dienstkonsolenfenstern, um die Dienste zu beenden.  
  
## <a name="configurable-via-code-or-appconfig"></a>Konfigurierbar über Code oder App.config  
 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert. Sie können außerdem den Namen der Datei RoutingService\App.config ändern, damit er nicht erkannt wird, und die Auskommentierung des Methodenaufrufs von `ConfigureRouterViaCode()` in RoutingService\routing.cs aufheben. Beide Methoden führen zum gleichen Routerverhalten.  
  
### <a name="scenario"></a>Szenario  
 In diesem Beispiel wird der Router als inhaltsbasierter Router dargestellt, der ermöglicht, dass mehrere Typen oder Implementierungen von Diensten über einen Endpunkt verfügbar gemacht werden.  
  
### <a name="real-world-scenario"></a>Reales Szenario  
 Contoso möchte sämtliche Dienste virtualisieren, um nur einen Endpunkt öffentlich verfügbar zu machen, über den Zugriff auf mehrere verschiedene Dienste gewährt wird. In diesem Fall werden die inhaltsbasierten Routingfunktionen des Routingdiensts verwendet, um zu bestimmen, wohin die eingehenden Anforderungen gesendet werden sollen.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
