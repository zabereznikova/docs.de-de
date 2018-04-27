---
title: Erweiterte Fehlerbehandlung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35911a80e7686a1023f42115f785fb64d949aeff
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="advanced-error-handling"></a>Erweiterte Fehlerbehandlung
In diesem Beispiel wird der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Routingdienst veranschaulicht. Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht. In diesem Beispiel wird gezeigt, wie der Routingdienst eine intelligente Fehlerwiederherstellung mit Transaktionen und anderen komplexen Messagingkonzepten (z. B. Multicasting) ausführt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel wird der Routingdienst konfiguriert, um eine Nachricht aus einer MSMQ-Warteschlange zu lesen und die Nachricht per Multicast an zwei Warteschlangenlisten zu senden. Eine Liste wird für Dienstwarteschlangen verwendet, die andere für Protokollwarteschlangen.  
  
 Da die MSMQ-Bindung, die der Routingdienst laut Konfiguration verwenden soll, normalerweise die Verwendung von Transaktionen unterstützt, stellt der Routingdienst sicher, dass die Meldung transaktionsfähig ist und von mindestens einer Warteschlange in jeder Liste empfangen wurde. Erst dann wird eine Meldung an die eingehende Warteschlange (`InQ`) gesendet, dass die Nachricht erfolgreich geroutet wurde. Wenn deshalb beide Dienstwarteschlangen oder beide Protokollwarteschlangen nicht verfügbar sind, meldet der Routingdienst, dass die Nachricht nicht geroutet werden konnte und die eingehende Warteschlange eine Aktion ausführen sollte. Diese Aktion besteht darin, dass die Nachricht in die Systemwarteschlange für unzustellbare Meldungen verschoben wird.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  > [!IMPORTANT]
    >  Installieren Sie MSMQ, bevor Sie dieses Beispiel ausführen. Wenn MSMQ nicht installiert ist, wird beim Ausführen des Beispiels eine Ausnahmemeldung zurückgegeben. Anweisungen zum Installieren von MSMQ finden Sie unter [Installieren von Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).  
  
     Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] AdvancedErrorHandling.sln.  
  
2.  Drücken Sie **F5** oder **STRG + UMSCHALT + B** in Visual Studio.  
  
    1.  Wenn Sie die Anwendung mit STRT+UMSCHALT+B erstellen, müssen Sie die Anwendung mit ./RoutingService/bin/debug/RoutingService.exe starten.  
  
3.  Drücken Sie die EINGABETASTE im Konsolenfenster, um den Client zu starten.  
  
4.  Der Client gibt für jeden Fall eine andere Statistik zu den Warteschlangen zurück.  
  
    1.  Folgende Ausgabe wird in Fall 1 zurückgegeben (keine Fehler).  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  Folgende Ausgabe wird in Fall 3 zurückgegeben (Fehler beim primären Dienst und der Protokollierungswarteschlange).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  Folgende Ausgabe wird in Fall 4 zurückgegeben (Fehler bei der primären Dienstwarteschlange und bei der primären und Sicherungsprotokollierungswarteschlange).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  Folgende Ausgabe wird in Fall 2 zurückgegeben (Fehler bei der primären Dienstwarteschlange).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Konfigurierbar über Code oder App.config  
 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert. Sie können auch den Namen der Datei RoutingService\App.config ändern, damit diese nicht erkannt wird, und den Wert des `configDriven`-Felds in RoutingService\Program.cs auf `false` festlegen, um die im Code definierte Konfiguration zu verwenden. Beide Methoden führen zum gleichen Routerverhalten.  
  
### <a name="scenario"></a>Szenario  
 In diesem Beispiel wird gezeigt, dass der Routingdienst erweiterte Messagingfunktionen behandeln kann, z. B. Transaktions- und Empfangskontext, und dass es diese Funktionen als Bestandteil der ordnungsgemäßen Behandlung von Fehlerszenarien verwenden kann.  
  
### <a name="real-world-scenario"></a>Reales Szenario  
 Contoso möchte transaktionale Empfangsprozesse über den Routingdienst verwenden, um sicherzustellen, dass alle erforderlichen Dienste die Informationen auch beim Auftreten von Fehlern empfangen. Außerdem sollen Fehler richtig und automatisch behandelt und Fehler gemeldet werden, falls eine Nachricht auch dann nicht zugestellt werden kann, wenn die Fehlerbehandlungslogik verwendet wird. Zu diesem Zweck wird der Routingdienst so konfiguriert, dass erwartungsgemäß ein Failover zu bestimmten Endpunkten ausgeführt wird. Der Routingdienst behandelt ggf. Fehlersituationen einschließlich Erstellung, Abschluss und Rollback/Abbrechen von Transaktionen/Empfangskontexten.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
