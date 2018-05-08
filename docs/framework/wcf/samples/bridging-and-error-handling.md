---
title: Überbrückung und Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
ms.openlocfilehash: f13a55704422e8a958e55c489f6db11108b03c90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bridging-and-error-handling"></a>Überbrückung und Fehlerbehandlung
Dieses Beispiel veranschaulicht die Verwendung des Windows Communication Foundation (WCF)-Routingdienst zum Überbrücken von Kommunikation zwischen einem Client und einem Dienst mit unterschiedliche Bindungen verwendet. In diesem Beispiel wird auch gezeigt, wie ein Sicherungsdienst für Failoverszenarien verwendet wird. Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht. In diesem Beispiel wird das standardmäßige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel ist der Rechnerclient so konfiguriert, dass er Nachrichten an einen vom Router verfügbar gemachten Endpunkt sendet. Der Routingdienst ist so konfiguriert, dass er alle gesendeten Nachrichten akzeptiert und diese an einen Endpunkt weiterleitet, der dem Rechnerdienst entspricht. Die folgenden Punkte beschreiben die Konfiguration des primären Rechnerdiensts, des Sicherungsrechnerdiensts und des Rechnerclients. Außerdem wird erläutert, wie die Kommunikation zwischen dem Client und dem Dienst mithilfe des Routingdiensts erfolgt:  
  
-   Der Rechnerclient ist für die Verwendung von BasicHttpBinding und der Rechnerdienst für die Verwendung von NetTcpBinding eingerichtet. Wenn erforderlich, konvertiert der Routingdienst die Nachrichten automatisch, bevor er sie an den Rechnerdienst sendet, und er konvertiert außerdem die Antworten, damit der Rechnerclient auf sie zugreifen kann.  
  
-   Der Routingdienst kennt zwei Rechnerdienste: den primären Rechnerdienst und den Sicherungsrechnerdienst. Der Routingdienst versucht zuerst, mit dem primären Rechnerdienstendpunkt zu kommunizieren. Wenn der Endpunkt deaktiviert ist und dieser Versuch fehlschlägt, versucht der Routingdienst, mit dem Sicherungsrechnerdienstendpunkt zu kommunizieren.  
  
 Somit werden vom Client gesendete Nachrichten vom Router empfangen und zum eigentlichen Rechnerdienst umgeleitet. Wenn der Rechnerdienstendpunkt deaktiviert ist, leitet der Routingdienst die Nachricht an den Sicherungsrechnerdienstendpunkt weiter. Nachrichten vom Sicherungsrechnerdienst werden an den Dienstrouter zurückgesendet, der sie dann zurück an den Rechnerclient übergibt.  
  
> [!NOTE]
>  Für eine Sicherungsliste kann mehr als ein Endpunkt definiert sein. Wenn in diesem Fall der Sicherungsdienstendpunkt deaktiviert ist, versucht der Routingdienst solange, eine Verbindung mit dem nächsten Sicherungsendpunkt in der Liste herzustellen, bis die Verbindung besteht.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie RouterBridgingAndErrorHandling.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie F5 oder STRG+UMSCHALT+B in Visual Studio.  
  
    1.  Wenn Sie möchten die notwendigen Projekte automatisch gestartet, wenn Sie F5 drücken, mit der rechten Maustaste in der Projektmappe, wählen Sie **Eigenschaften**, und klicken Sie in der **Startprojekt** Knoten unter **allgemeine Eigenschaften**Option **mehrere Startprojekte**, und legen Sie alle Projekte auf **starten**.  
  
    2.  Wenn Sie das Projekt mit STRG+UMSCHALT+B erstellen, müssen Sie die folgenden Anwendungen starten:  
  
        1.  Rechnerclient (./CalculatorClient/bin/client.exe)  
  
        2.  Rechnerdienst (./CalculatorService/bin/service.exe)  
  
        3.  Routingdienst (./RoutingService/bin/RoutingService.exe)  
  
3.  Drücken Sie auf dem Rechnerclient die EINGABETASTE, um den Client zu starten.  
  
     Die folgende Ausgabe wird angezeigt:  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Konfigurierbar über Code oder App.config  
 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert. Sie können außerdem den Namen der Datei App.config ändern, damit er nicht erkannt wird, und die Auskommentierung des Methodenaufrufs von `ConfigureRouterViaCode()` aufheben. Beide Methoden führen zum gleichen Routerverhalten.  
  
### <a name="scenario"></a>Szenario  
 In diesem Beispiel wird die Funktionsweise des Dienstrouters als Protokollbrücke und Fehlerhandler veranschaulicht. In diesem Szenario tritt kein inhaltsbasiertes Routing auf. Der Routingdienst fungiert als transparenter Proxyknoten, der für die direkte Übergabe der Nachrichten an einen vorkonfigurierten Satz von Zielendpunkten eingerichtet wurde. Der Routingdienst führt auch die zusätzlichen Schritte der transparenten Behandlung von Fehlern aus, die auftreten, wenn er versucht, Nachrichten an die Endpunkte zu senden, mit denen er gemäß seiner Konfiguration kommunizieren soll. Indem der Routingdienst als Protokollbrücke fungiert, ermöglicht er dem Benutzer, ein Protokoll für die externe Kommunikation und ein anderes Protokoll für die interne Kommunikation zu definieren.  
  
### <a name="real-world-scenario"></a>Reales Szenario  
 Contoso möchte einen interoperablen Dienstendpunkt für die Umgebung bereitstellen und gleichzeitig die interne Leistung optimieren. Aus diesem Grund werden die Dienste über einen Endpunkt mithilfe von BasicHttpBinding für die Umgebung verfügbar gemacht, während intern der Routingdienst für die Überbrückung der Verbindung mit dem Endpunkt verwendet wird. Dies erfolgt mithilfe der vom Dienst verwendeten NetTcpBinding. Weiterhin soll das Dienstangebot von Contoso gegenüber temporären Ausfällen der Produktionsdienste tolerant sein. Aus diesem Grund werden mehrere Endpunkte hinter dem Routerdienst virtualisiert, und bei einem Fehler erfolgt mithilfe der Fehlerbehandlungsfunktionen ein automatischer Wechsel zu den Sicherungsendpunkten, wenn erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
