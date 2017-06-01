---
title: "Zugreifen auf OperationContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Zugreifen auf OperationContext
Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten \(<xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.Send>\) mit einer benutzerdefinierten Bereichsaktivität verwendet werden können, um auf <xref:System.ServiceModel.OperationContext.Current%2A> zuzugreifen und einen benutzerdefinierten Nachrichtenheader in einer ausgehenden oder eingehenden Nachricht anzufügen oder abzurufen.  
  
## Veranschaulicht  
 Messagingaktivitäten, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>  
  
## Diskussion  
 In diesem Beispiel wird gezeigt, wie Erweiterungspunkte \(<xref:System.ServiceModel.Activities.ISendMessageCallback>,  <xref:System.ServiceModel.Activities.IReceiveMessageCallback>\) in Messagingaktivitäten verwendet werden, um auf <xref:System.ServiceModel.OperationContext.Current%2A> zuzugreifen.Die Rückrufe werden innerhalb der Workflowlaufzeit als eine Implementierung von <xref:System.Activities.IExecutionProperty> registriert, die von den Messagingaktivitäten nach der Ausführung abgerufen wird.Jede Messagingaktivität im gleichen Bereich wie die <xref:System.Activities.IExecutionProperty>\-Implementierung ist betroffen.Insbesondere erzwingt dieses Beispiel das Rückrufverhalten mithilfe einer benutzerdefinierten Bereichsaktivität.<xref:System.ServiceModel.Activities.ISendMessageCallback> wird im Clientworkflow verwendet, um <xref:System.Activities.WorkflowApplication.Id%2A> des Workflows als ausgehenden <xref:System.ServiceModel.Channels.MessageHeader> einzuschließen.Dieser Header wird dann im Dienst mit <xref:System.ServiceModel.Activities.IReceiveMessageCallback> abgerufen, und der Wert des Headers wird auf der Konsole ausgegeben.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP\-Endpunkten verfügbar.Um dieses Beispiel auszuführen, müssen richtige URL\-ACLs hinzugefügt werden \(weitere Informationen finden Sie unter [Konfigurieren von HTTP und HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)\), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten, um die entsprechenden ACLs hinzuzufügen.Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Sobald die URL\-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1.  Erstellen Sie die Projektmappe.  
  
    2.  Legen Sie mehrere Startprojekte fest, indem Sie mit der rechten Maustaste auf die Projektmappe klicken und **Startprojekte festlegen** auswählen.  
  
    3.  Füge Sie **Dienst** und **Client** \(in dieser Reihenfolge\) als mehrere Startprojekte hinzu.  
  
    4.  Führen Sie die Anwendung aus.Die Clientkonsole zeigt einen Workflow an, der zweimal ausgeführt wird, und das Dienstfenster zeigt die Instanz\-ID dieser Workflows an.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`