---
title: Zugreifen auf OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 83f3a6cacd3ee86050f65a886d446ab8da7d3690
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094708"
---
# <a name="accessing-operationcontext"></a>Zugreifen auf OperationContext
In diesem Beispiel wird veranschaulicht, wie die Messaging Aktivitäten (<xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.Send>) mit einer benutzerdefinierten Bereichs Aktivität verwendet werden können, um auf <xref:System.ServiceModel.OperationContext.Current%2A> zuzugreifen und einen benutzerdefinierten Nachrichten Header in einer ausgehenden oder eingehenden Nachricht anzufügen oder abzurufen.  
  
## <a name="demonstrates"></a>Zeigt  
 Messagingaktivitäten, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie Erweiterungspunkte (<xref:System.ServiceModel.Activities.ISendMessageCallback>,  <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in Messagingaktivitäten verwendet werden, um auf <xref:System.ServiceModel.OperationContext.Current%2A> zuzugreifen. Die Rückrufe werden innerhalb der Workflowlaufzeit als eine Implementierung von <xref:System.Activities.IExecutionProperty> registriert, die von den Messagingaktivitäten nach der Ausführung abgerufen wird. Jede Messagingaktivität im gleichen Bereich wie die <xref:System.Activities.IExecutionProperty>-Implementierung ist betroffen. Insbesondere erzwingt dieses Beispiel das Rückrufverhalten mithilfe einer benutzerdefinierten Bereichsaktivität. <xref:System.ServiceModel.Activities.ISendMessageCallback> wird im Clientworkflow verwendet, um <xref:System.Activities.WorkflowApplication.Id%2A> des Workflows als ausgehenden <xref:System.ServiceModel.Channels.MessageHeader> einzuschließen. Dieser Header wird dann im Dienst mit <xref:System.ServiceModel.Activities.IReceiveMessageCallback> abgerufen, und der Wert des Headers wird auf der Konsole ausgegeben.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar. Zum Ausführen dieses Beispiels müssen die richtigen URL-ACLs hinzugefügt werden (Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](../../wcf/feature-details/configuring-http-and-https.md) ), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten, um die entsprechenden ACLs hinzuzufügen. Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Sobald die URL-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1. Erstellen Sie die Projektmappe.  
  
    2. Legen Sie mehrere Start Projekte fest, indem Sie mit der rechten Maustaste auf die Projekt Mappe Klicken und **Start Projekte festlegen**auswählen.  
  
    3. Fügen Sie den **Dienst** und den **Client** (in dieser Reihenfolge) als mehrere Start Projekte hinzu.  
  
    4. Führen Sie die Anwendung aus. Die Clientkonsole zeigt einen Workflow an, der zweimal ausgeführt wird, und das Dienstfenster zeigt die Instanz-ID dieser Workflows an.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
