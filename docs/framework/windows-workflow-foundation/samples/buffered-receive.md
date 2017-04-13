---
title: "Gepuffertes Empfangen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Gepuffertes Empfangen
In diesem Beispiel wird veranschaulicht, wie die gepufferte Empfangsfunktion in [!INCLUDE[wf](../../../../includes/wf-md.md)] eingerichtet und konfiguriert wird.Die gepufferte Empfangsfunktion ermöglicht es dem Workflowautor, einen Workflow zu erstellen, ohne sich Gedanken über die Reihenfolge zu machen, in der Nachrichten empfangen werden.Die gepufferte Empfangsfunktion puffert Nachrichten lokal und übermittelt sie, wenn der Workflow zum Empfang bereit ist.  
  
## Veranschaulicht  
 Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge unter Verwendung der gepufferten Empfangsfunktion mit Messagingaktivitäten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## Diskussion  
 In diesem Beispiel wird ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] implementiert, der über eine Abfolge von <xref:System.ServiceModel.Activities.Receive>\-Aktivitäten verfügt.Dieser Workflow modelliert einen einfachen Kreditgenehmigungsprozess, bei dem der Workflow drei Benachrichtigungen erwartet, bevor ein Kredit genehmigt wird.Eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clientanwendung sendet drei korrelierende Benachrichtigungen in umgekehrter Reihenfolge als die, die der Dienst erwartet.Da die gepufferte Empfangsfunktion für den Dienst aktiviert ist, wird jede Nachricht, die sich außerhalb der normalen Reihenfolge befindet, beim Dienst gepuffert und verarbeitet, wenn der Workflow für den Empfang bereit ist.  
  
 Die gepufferte Empfangsfunktion erfordert <xref:System.ServiceModel.Activities.ReceiveContent>\-Unterstützung durch die Bindung. Daher verwendet der Dienst <xref:System.ServiceModel.NetMsmqBinding>.Für die Bindung ist keine spezielle Konfiguration erforderlich, sodass die Standardwerte verwendet werden.  
  
```  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
  
```  
  
 Der Dienst macht mithilfe von <xref:System.ServiceModel.Description.ServiceMetadataBehavior> außerdem Metadaten für den Dienst verfügbar.  
  
 Auf ähnliche Weise wird der Clientendpunkt mit <xref:System.ServiceModel.NetMsmqBinding> konfiguriert.Der Clientcode und die Konfiguration werden mit der Funktion **Dienstverweis hinzufügen** von [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] generiert.Das folgende Beispiel stellt den generierten Clientendpunkt in der Datei App.config dar.  
  
```  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
  
```  
  
 Dieses Beispiel erfordert, dass die folgenden Windows\-Komponenten aktiviert sind:  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]\-Verwaltungskompatibilität, \-Metabasis und \-Konfigurationskompatibilität  
  
3.  World Wide Web\-Dienst, Anwendungsentwicklungsfunktionen und ASP.NET  
  
4.  Microsoft Message Queues \(MSMQ\) Server  
  
#### So richten Sie das Beispiel ein und erstellen es  
  
1.  Registrieren Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Eingabeaufforderung ASP.NET, indem Sie `aspnet_regiis –I` eingeben, und drücken Sie die EINGABETASTE.  
  
2.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] als Administrator aus.  
  
3.  Öffnen Sie LoanService.sln.  
  
4.  Bestätigen Sie die Frage, ob die virtuellen Verzeichnisse für das LoanService\-Projekt erstellt werden solle, mit **Ja**.  
  
#### So richten Sie die Dienstwarteschlangen ein  
  
1.  Drücken Sie F5, um die LoanClient\-Anwendung, die die Warteschlangen erstellt und den in Service1.xaml definierten Dienst aktiviert, auszuführen.  
  
2.  Öffnen Sie die **Computerverwaltungskonsole**, indem Sie Compmgmt.msc an einer Eingabeaufforderung ausführen.  
  
3.  Erweitern Sie in der **Computerverwaltungskonsole** den Eintrag **Dienst**, **Anwendungen**, **Message Queuing**, **Private Warteschlangen**.  
  
4.  Klicken Sie mit der rechten Maustaste auf die Warteschlange loanservice\/service1.xamlx, und wählen Sie **Eigenschaften** aus.  
  
5.  Wählen Sie die Registerkarte **Sicherheit** aus, und fügen Sie die Berechtigungen **Nachricht empfangen**, **Nachricht einsehen** und **Nachricht senden** hinzu.  
  
6.  Öffnen Sie den [!INCLUDE[iis60](../../../../includes/iis60-md.md)]\-Manager.  
  
7.  Wechseln Sie zu **Server**, **Sites**, **Standardwebsite**, **Privat**, **LoanService**, und wählen Sie **Erweiterte Optionen** aus.  
  
8.  Ändern Sie **Aktivierte Protokolle** in **http**, **net.msmq**.  
  
#### So führen Sie das Beispiel aus  
  
1.  Wechseln Sie zu http:\/\/localhost\/private\/loanservice\/service1.xamlx, um sicherzustellen, dass der Dienst ausgeführt wird.  
  
2.  Drücken Sie F5, um die LoanClient\-Anwendung auszuführen.Sobald der Workflow abgeschlossen ist, wird eine out.txt\-Datei unter C:\\Inbox gespeichert, die das Ergebnis des Nachrichtenaustauschs enthält.  
  
#### So führen Sie eine Bereinigung durch  
  
1.  Öffnen Sie die **Computerverwaltungskonsole**, indem Sie Compmgmt.msc an einer Eingabeaufforderung ausführen.  
  
2.  Erweitern Sie **Dienste** und **Anwendungen**, **Message Queuing**, **Private Warteschlangen**.  
  
3.  Löschen Sie die Warteschlange loanservice\/service1.xamlx.  
  
4.  Entfernen Sie das Verzeichnis C:\\Inbox.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`