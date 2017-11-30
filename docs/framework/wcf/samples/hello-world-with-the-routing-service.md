---
title: Hello World mit dem Routingdienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a03f3eeab6ce30c011a6f67c64cc3997130c895
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="hello-world-with-the-routing-service"></a>Hello World mit dem Routingdienst
In diesem Beispiel wird der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Routingdienst veranschaulicht. Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht. In diesem Beispiel wird das standardmäßige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst. In diesem Beispiel ist der Rechnerclient so konfiguriert, dass er Nachrichten an einen vom Router verfügbar gemachten Endpunkt sendet. Der Routingdienst ist so konfiguriert, dass er alle gesendeten Nachrichten akzeptiert und diese an einen Endpunkt weiterleitet, der dem Rechnerdienst entspricht. Somit werden vom Client gesendete Nachrichten vom Router empfangen und zum eigentlichen Rechnerdienst umgeleitet. Nachrichten vom Rechnerdienst werden an den Router zurückgesendet, der sie dann zurück an den Rechnerclient übergibt.  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
