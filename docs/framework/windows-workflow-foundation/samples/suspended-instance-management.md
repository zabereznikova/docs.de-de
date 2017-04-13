---
title: "Angehaltene Instanzverwaltung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Angehaltene Instanzverwaltung
In diesem Beispiel wird veranschaulicht, wie Workflowinstanzen, die angehalten wurden, verwaltet werden.Die Standardaktion für <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist `AbandonAndSuspend`.Dies bedeutet, dass nicht behandelte Ausnahmen, die von einer Workflowinstanz ausgelöst werden, die im <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, standardmäßig dazu führen, dass die Instanz aus dem Speicher verworfen \(abgebrochen\) und dass die dauerhafte\/persistente Version der Instanz als angehalten markiert wird.Eine angehaltene Workflowinstanz kann erst ausgeführt werden, nachdem sie fortgesetzt wurde.  
  
 Das Beispiel zeigt, wie ein Befehlszeilenprogramm implementiert werden kann, um angehaltene Instanzen abzufragen, und wie dem Benutzer die Option gegeben wird, um die Instanz fortzusetzen oder zu beenden.In diesem Beispiel löst ein Workflowdienst absichtlich eine Ausnahme aus, wodurch verursacht wird, dass er angehalten wird.Das Befehlszeilenprogramm kann dann verwendet werden, um die Instanz abzufragen und anschließend die Instanz fortzusetzen oder zu beenden.  
  
## Veranschaulicht  
 <xref:System.ServiceModel.WorkflowServiceHost> mit <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> und <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## Diskussion  
 Das in diesem Beispiel implementierte Befehlszeilenprogramm ist speziell auf die SQL\-Instanzspeicherimplementierung ausgerichtet, die in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthalten ist.Wenn Sie über eine benutzerdefinierte Implementierung des Instanzspeichers verfügen, können Sie dieses Hilfsprogramm anpassen, indem Sie die `WorkflowInstanceCommand`\-Implementierungen im Beispiel durch Implementierungen speziell für Ihren Instanzspeicher ersetzen.  
  
 Die bereitgestellte Implementierung führt SQL\-Befehle direkt für den SQL\-Instanzspeicher aus, um angehaltene Instanzen direkt aufzuführen, und diese basiert auf einem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>, der dem <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt wurde, um die Instanzen fortzusetzen oder zu beenden.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Dieses Beispiel erfordert, dass die folgenden Windows\-Komponenten aktiviert sind:  
  
    1.  Microsoft Message Queues \(MSMQ\) Server  
  
    2.  SQL Server Express  
  
2.  Richten Sie die SQL Server\-Datenbank ein.  
  
    1.  Führen Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Eingabeaufforderung den Befehl "setup.cmd" aus dem Beispielverzeichnis "SuspendedInstanceManagement", wodurch Folgendes bewirkt wird:  
  
        1.  Erstellung einer Persistenzdatenbank mit SQL Server Express.Wenn die Persistenzdatenbank bereits vorhanden ist, dann wird diese gelöscht und neu erstellt.  
  
        2.  Einrichten der Datenbank für Persistenz.  
  
        3.  Fügt IIS der InstanceStoreUsers\-Rolle, die beim Einrichten der Datenbank für Persistenz definiert wurde, APPPOOL\\DefaultAppPool und NT AUTHORITY\\Network Service hinzu.  
  
3.  Einrichten der Dienstwarteschlange.  
  
    1.  Klicken Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit der rechten Maustaste auf das Projekt **SampleWorkflowApp**, und klicken Sie auf **Als Startprojekt festlegen**.  
  
    2.  Kompilieren Sie die SampleWorkflowApp aus, und führen Sie sie aus, indem Sie **F5** drücken.Dadurch wird die erforderliche Warteschlange erstellt.  
  
    3.  Drücken Sie die **EINGABETASTE**, um die SampleWorkflowApp zu beenden.  
  
    4.  Öffnen Sie die Computerverwaltungskonsole, indem Sie "Compmgmt.msc" an einer Eingabeaufforderung ausführen.  
  
    5.  Erweitern Sie **Dienste und Anwendungen**, **Message Queuing**, **Private Warteschlangen**.  
  
    6.  Klicken Sie mit der rechten Maustaste auf die Warteschlange **ReceiveTx**, und wählen Sie **Eigenschaften** aus.  
  
    7.  Wählen Sie die Registerkarte **Sicherheit** aus, und gewähren Sie allen die Berechtigung **Nachricht empfangen**, **Nachricht einsehen** und **Nachricht senden**.  
  
4.  Führen Sie nun das Beispiel aus.  
  
    1.  Führen Sie das Projekt "SampleWorkflowApp" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] erneut ohne Debugging aus, indem Sie **STRG\+F5** drücken.Zwei Endpunktadressen werden im Konsolenfenster ausgegeben: eine für den Anwendungsendpunkt und die andere vom <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.Daraufhin wird eine Workflowinstanz erstellt, und Überwachungsdatensätze für diese Instanz werden im Konsolenfenster angezeigt.Die Workflowinstanz löst eine Ausnahme aus, die bewirkt, dass die Instanz angehalten und abgebrochen wird.  
  
    2.  Das Befehlszeilenprogramm kann dann verwendet werden, um weitere Aktionen für diese Instanzen auszuführen.Die Syntax für Befehlszeilenargumente ist wie folgt:  
  
         `SuspendedInstanceManagement - Befehl:[CommandName] - Server:[ServerName] - Datenbank:[DatabaseName] - InstanceID:[InstanceId]`  
  
         Die unterstützten Befehle sind: `Query`, `Resume` und `Terminate`.Der InstanceId\-Schalter ist nur für `Resume`\- und `Terminate`\-Vorgänge erforderlich.  
  
#### So führen Sie eine \(optionale\) Bereinigung durch  
  
1.  Öffnen Sie die Computerverwaltungskonsole, indem Sie "Compmgmt.msc" an einer `vs2010`\-Eingabeaufforderung ausführen.  
  
2.  Erweitern Sie **Dienste und Anwendungen**, **Message Queuing**, **Private Warteschlangen**.  
  
3.  Löschen Sie die **ReceiveTx**\-Warteschlange.  
  
4.  Um die Persistenzdatenbank zu entfernen, führen Sie "cleanup.cmd" aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`