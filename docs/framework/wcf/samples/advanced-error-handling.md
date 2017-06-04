---
title: "Erweiterte Fehlerbehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Erweiterte Fehlerbehandlung
In diesem Beispiel wird der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Routingdienst veranschaulicht.  Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht.  In diesem Beispiel wird gezeigt, wie der Routingdienst eine intelligente Fehlerwiederherstellung mit Transaktionen und anderen komplexen Messagingkonzepten \(z. B. Multicasting\) ausführt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## Beispieldetails  
 In diesem Beispiel wird der Routingdienst konfiguriert, um eine Nachricht aus einer MSMQ\-Warteschlange zu lesen und die Nachricht per Multicast an zwei Warteschlangenlisten zu senden.  Eine Liste wird für Dienstwarteschlangen verwendet, die andere für Protokollwarteschlangen.  
  
 Da die MSMQ\-Bindung, die der Routingdienst laut Konfiguration verwenden soll, normalerweise die Verwendung von Transaktionen unterstützt, stellt der Routingdienst sicher, dass die Meldung transaktionsfähig ist und von mindestens einer Warteschlange in jeder Liste empfangen wurde. Erst dann wird eine Meldung an die eingehende Warteschlange \(`InQ`\) gesendet, dass die Nachricht erfolgreich geroutet wurde.  Wenn deshalb beide Dienstwarteschlangen oder beide Protokollwarteschlangen nicht verfügbar sind, meldet der Routingdienst, dass die Nachricht nicht geroutet werden konnte und die eingehende Warteschlange eine Aktion ausführen sollte.  Diese Aktion besteht darin, dass die Nachricht in die Systemwarteschlange für unzustellbare Meldungen verschoben wird.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  > [!IMPORTANT]
    >  Installieren Sie MSMQ, bevor Sie dieses Beispiel ausführen.  Wenn MSMQ nicht installiert ist, wird beim Ausführen des Beispiels eine Ausnahmemeldung zurückgegeben.  Anweisungen zum Installieren von MSMQ finden Sie unter [Installieren von Message Queuing \(MSMQ\)](http://go.microsoft.com/fwlink/?LinkId=166437).  
  
     Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] AdvancedErrorHandling.sln.  
  
2.  Drücken Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] **F5** oder **STRG\+UMSCHALT\+B**.  
  
    1.  Wenn Sie die Anwendung mit STRT\+UMSCHALT\+B erstellen, müssen Sie die Anwendung mit .\/RoutingService\/bin\/debug\/RoutingService.exe starten.  
  
3.  Drücken Sie die EINGABETASTE im Konsolenfenster, um den Client zu starten.  
  
4.  Der Client gibt für jeden Fall eine andere Statistik zu den Warteschlangen zurück.  
  
    1.  Folgende Ausgabe wird in Fall 1 zurückgegeben \(keine Fehler\).  
  
        ```Output  
  
                            Die eingehende Warteschlange weist 0 Meldungen auf.  
  
        Die primäre Dienstwarteschlange weist 1 Meldung auf.  
  
        Die Sicherungsdienstwarteschlange weist 0 Meldungen auf.  
  
        Die primäre Protokollierungswarteschlange weist 1 Meldung auf.  
  
        Die Sicherungsprotokollierungswarteschlange weist 0 Meldungen auf.  
  
        Drücken Sie die <EINGABETASTE>, um den Vorgang fortzusetzen.  
  
        ```  
  
    2.  Folgende Ausgabe wird in Fall 3 zurückgegeben \(Fehler beim primären Dienst und der Protokollierungswarteschlange\).  
  
        ```Output  
  
        Die eingehende Warteschlange weist 0 Meldungen auf.  
  
        Die primäre Dienstwarteschlange ist nicht vorhanden.  
  
        Die Sicherungsdienstwarteschlange weist 1 Meldungen auf.  
  
        Die primäre Protokollierungswarteschlange ist nicht vorhanden.  
  
        Die Sicherungsprotokollierungswarteschlange weist 1 Meldungen auf.  
  
        Drücken Sie die <EINGABETASTE>, um den Vorgang fortzusetzen.  
  
        ```  
  
    3.  Folgende Ausgabe wird in Fall 4 zurückgegeben \(Fehler bei der primären Dienstwarteschlange und bei der primären und Sicherungsprotokollierungswarteschlange\).  
  
        ```Output  
  
                            Die eingehende Warteschlange weist 0 Meldungen auf.  
  
        Die primäre Dienstwarteschlange ist nicht vorhanden.  
  
        Die Sicherungsdienstwarteschlange weist 0 Meldungen auf.  
  
        Die primäre Protokollierungswarteschlange ist nicht vorhanden.  
  
        Die Sicherungsprotokollierungswarteschlange ist nicht vorhanden.  
  
        Die Systemwarteschlange für unzustellbare Meldungen weist 1 Meldung auf.  
  
        Drücken Sie die <EINGABETASTE>, um den Vorgang zu beenden.  
  
        ```  
  
    4.  Folgende Ausgabe wird in Fall 2 zurückgegeben \(Fehler bei der primären Dienstwarteschlange\).  
  
        ```Output  
  
                            Die eingehende Warteschlange weist 0 Meldungen auf.  
  
        Die primäre Dienstwarteschlange ist nicht vorhanden.  
  
        Die Sicherungsdienstwarteschlange weist 1 Meldungen auf.  
  
        Die primäre Protokollierungswarteschlange weist 1 Meldung auf.  
  
        Die Sicherungsprotokollierungswarteschlange weist 0 Meldungen auf.  
  
        Drücken Sie die <EINGABETASTE>, um den Vorgang fortzusetzen.  
  
        ```  
  
## Konfigurierbar über Code oder App.config  
 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert.  Sie können auch den Namen der Datei RoutingService\\App.config ändern, damit diese nicht erkannt wird, und den Wert des `configDriven`\-Felds in RoutingService\\Program.cs auf `false` festlegen, um die im Code definierte Konfiguration zu verwenden.  Beide Methoden führen zum gleichen Routerverhalten.  
  
### Szenario  
 In diesem Beispiel wird gezeigt, dass der Routingdienst erweiterte Messagingfunktionen behandeln kann, z. B. Transaktions\- und Empfangskontext, und dass es diese Funktionen als Bestandteil der ordnungsgemäßen Behandlung von Fehlerszenarien verwenden kann.  
  
### Reales Szenario  
 Contoso möchte transaktionale Empfangsprozesse über den Routingdienst verwenden, um sicherzustellen, dass alle erforderlichen Dienste die Informationen auch beim Auftreten von Fehlern empfangen.  Außerdem sollen Fehler richtig und automatisch behandelt und Fehler gemeldet werden, falls eine Nachricht auch dann nicht zugestellt werden kann, wenn die Fehlerbehandlungslogik verwendet wird.  Zu diesem Zweck wird der Routingdienst so konfiguriert, dass erwartungsgemäß ein Failover zu bestimmten Endpunkten ausgeführt wird. Der Routingdienst behandelt ggf. Fehlersituationen einschließlich Erstellung, Abschluss und Rollback\/Abbrechen von Transaktionen\/Empfangskontexten.  
  
## Siehe auch  
 [AppFabric\-Hosting\- und \-Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)