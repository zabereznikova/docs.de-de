---
title: Hello World mit dem Routingdienst
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 881636097cf342de09164804c6df6acfbcd97c45
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="hello-world-with-the-routing-service"></a>Hello World mit dem Routingdienst
Diesem Beispiel wird der Windows Communication Foundation (WCF)-Routingdienst veranschaulicht. Der Routingdienst ist eine WCF-Komponente, die integrieren ein inhaltsbasierten Routers in die Anwendung aufnehmen vereinfacht. In diesem Beispiel wird die standard-WCF--Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst. In diesem Beispiel ist der Rechnerclient so konfiguriert, dass er Nachrichten an einen vom Router verfügbar gemachten Endpunkt sendet. Der Routingdienst ist so konfiguriert, dass er alle gesendeten Nachrichten akzeptiert und diese an einen Endpunkt weiterleitet, der dem Rechnerdienst entspricht. Somit werden vom Client gesendete Nachrichten vom Router empfangen und zum eigentlichen Rechnerdienst umgeleitet. Nachrichten vom Rechnerdienst werden an den Router zurückgesendet, der sie dann zurück an den Rechnerclient übergibt.  
  
### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie HelloRoutingService.sln mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie F5 oder STRG+UMSCHALT+B.  
  
    > [!NOTE]
    >  Wenn Sie F5 drücken, wird der Rechnerclient automatisch gestartet. Wenn Sie STRG+UMSCHALT+B (Erstellen) drücken, müssen Sie die folgenden Anwendungen selbst starten.  
    >   
    >  1.  Rechnerclient (./CalculatorClient/bin/client.exe)  
    > 2.  Rechnerdienst (./CalculatorService/bin/service.exe)  
    > 3.  Routingdienst (./RoutingService/bin/RoutingService.exe)  
  
3.  Drücken Sie die EINGABETASTE, um den Client zu starten.  
  
     Die folgende Ausgabe wird angezeigt:  
  
     Add(100,15.99) = 115.99  
  
     Subtract(145,76.54) = 68.46  
  
     Multiply(9,81.25) = 731.25  
  
     Divide(22,7) = 3.14285714285714  
  
## <a name="configurable-via-code-or-appconfig"></a>Konfigurierbar über Code oder App.Config  
 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert. Sie können außerdem den Namen der Datei App.config ändern, damit er nicht erkannt wird, und die Auskommentierung des Methodenaufrufs von ConfigureRouterViaCode() aufheben. Beide Methoden führen zum gleichen Routerverhalten.  
  
### <a name="scenario"></a>Szenario  
 In diesem Beispiel wird der Router in der Funktion als einfaches Nachrichtensystem veranschaulicht. Der Routingdienst funktioniert als transparenter Proxyknoten, der so konfiguriert wurde, dass er Nachrichten direkt an einen vorkonfigurierten Satz von Zielendpunkten übergibt.  
  
### <a name="real-world-scenario"></a>Reales Szenario  
 Contoso möchte mehr Flexibilität bei der Benennung, Adressierung, Konfiguration und Sicherheit der Dienste. Aus diesem Grund wird ein einfaches Nachrichtensystem vor die Dienste gesetzt, das als öffentlicher Endpunkt fungiert. So können zusätzliche Sicherheitsmaßnahmen vor den eigentlichen Diensten eingefügt werden, und skalierte Lösungen sowie die Dienstversionsverwaltung können später einfacher implementiert werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
