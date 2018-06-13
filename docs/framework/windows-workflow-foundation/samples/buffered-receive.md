---
title: Gepuffertes Empfangen
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: ee53edafc94fd5efd4e412b1b9198a8763b79462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518710"
---
# <a name="buffered-receive"></a>Gepuffertes Empfangen
Dieses Beispiel veranschaulicht das Einrichten und konfigurieren die gepufferte Empfangsfunktion in Windows Workflow Foundation (WF). Die gepufferte Empfangsfunktion ermöglicht es dem Workflowautor, einen Workflow zu erstellen, ohne sich Gedanken über die Reihenfolge zu machen, in der Nachrichten empfangen werden. Die gepufferte Empfangsfunktion puffert Nachrichten lokal und übermittelt sie, wenn der Workflow zum Empfang bereit ist.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge unter Verwendung der gepufferten Empfangsfunktion mit Messagingaktivitäten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird ein Windows Communication Foundation (WCF)-Dienst implementiert, mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] und verfügt über eine Sequenz von <xref:System.ServiceModel.Activities.Receive> Aktivitäten. Dieser Workflow modelliert einen einfachen Kreditgenehmigungsprozess, bei dem der Workflow drei Benachrichtigungen erwartet, bevor ein Kredit genehmigt wird. Eine Windows Communication Foundation (WCF)-Clientanwendung sendet drei korrelierende Benachrichtigungen in umgekehrter Reihenfolge der Dienst erwartet. Da die gepufferte Empfangsfunktion für den Dienst aktiviert ist, wird jede Nachricht, die sich außerhalb der normalen Reihenfolge befindet, beim Dienst gepuffert und verarbeitet, wenn der Workflow für den Empfang bereit ist.  
  
 Die gepufferte Empfangsfunktion erfordert <xref:System.ServiceModel.Activities.ReceiveContent>-Unterstützung durch die Bindung. Daher verwendet der Dienst <xref:System.ServiceModel.NetMsmqBinding>. Für die Bindung ist keine spezielle Konfiguration erforderlich, sodass die Standardwerte verwendet werden.  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 Der Dienst macht mithilfe von <xref:System.ServiceModel.Description.ServiceMetadataBehavior> außerdem Metadaten für den Dienst verfügbar.  
  
 Auf ähnliche Weise wird der Clientendpunkt mit <xref:System.ServiceModel.NetMsmqBinding> konfiguriert. Der Clientcode und-Konfiguration generiert, indem die **Hinzufügen eines Dienstverweises** Funktion von Visual Studio. Das folgende Beispiel stellt den generierten Clientendpunkt in der Datei App.config dar.  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 Dieses Beispiel erfordert, dass die folgenden Windows-Komponenten aktiviert sind:  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]-Verwaltungskompatibilität, -Metabasis und -Konfigurationskompatibilität  
  
3.  World Wide Web-Dienst, Anwendungsentwicklungsfunktionen und ASP.NET  
  
4.  Microsoft Message Queues (MSMQ) Server  
  
#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es  
  
1.  Registrieren Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung ASP.NET, indem Sie `aspnet_regiis –I` eingeben, und drücken Sie die EINGABETASTE.  
  
2.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] als Administrator aus.  
  
3.  Öffnen Sie LoanService.sln.  
  
4.  Wenn Sie gefragt werden, wenn Sie die virtuellen Verzeichnisse für das LoanService-Projekt erstellen möchten, wählen Sie **Ja**.  
  
#### <a name="to-set-up-the-service-queues"></a>So richten Sie die Dienstwarteschlangen ein  
  
1.  Drücken Sie F5, um die LoanClient-Anwendung, die die Warteschlangen erstellt und den in Service1.xaml definierten Dienst aktiviert, auszuführen.  
  
2.  Öffnen der **Computerverwaltung** Konsole, indem Sie compmgmt.msc an einer Eingabeaufforderung.  
  
3.  In der **Computerverwaltung** nacheinander **Service**, **Anwendungen**, **Message Queuing**, **Private Warteschlangen** .  
  
4.  Mit der rechten Maustaste in die Warteschlange loanservice/Service1.xamlx, und wählen Sie **Eigenschaften**.  
  
5.  Wählen Sie die **Sicherheit** Registerkarte, und fügen Sie **Nachricht empfangen**, **Peek Message** und **Send Message** Berechtigungen.  
  
6.  Öffnen Sie den [!INCLUDE[iis60](../../../../includes/iis60-md.md)]-Manager.  
  
7.  Navigieren Sie zu **Server**, **Sites**, **Standardwebsite**, **Private**, **LoanService** und auswählen **Erweiterte Optionen**  
  
8.  Ändern der **aktivierte Protokolle** werden **http**, **net.msmq**.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Navigieren Sie zu http://localhost/private/loanservice/service1.xamlx um sicherzustellen, dass der Dienst ausgeführt wird.  
  
2.  Drücken Sie F5, um die LoanClient-Anwendung auszuführen. Sobald der Workflow abgeschlossen ist, wird eine out.txt-Datei unter C:\Inbox gespeichert, die das Ergebnis des Nachrichtenaustauschs enthält.  
  
#### <a name="to-clean-up"></a>So führen Sie eine Bereinigung durch  
  
1.  Öffnen der **Computerverwaltung** Konsole, indem Sie compmgmt.msc an einer Eingabeaufforderung.  
  
2.  Erweitern Sie **Service** und **Anwendungen**, **Message Queuing-**, **Private Warteschlangen**.  
  
3.  Löschen Sie die Warteschlange loanservice/service1.xamlx.  
  
4.  Entfernen Sie das Verzeichnis C:\Inbox.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
