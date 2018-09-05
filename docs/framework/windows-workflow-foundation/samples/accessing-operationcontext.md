---
title: Zugreifen auf OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 3c7ce1c9c37ee93b58a07376e0aeae045f0ca408
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43735487"
---
# <a name="accessing-operationcontext"></a>Zugreifen auf OperationContext
In diesem Beispiel wird veranschaulicht, wie die messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.Send>) mit einer benutzerdefinierten bereichsaktivität verwendet werden können, um den Zugriff auf <xref:System.ServiceModel.OperationContext.Current%2A> und anzufügen oder einen benutzerdefinierten Nachrichtenheader in einer ausgehenden oder eingehenden Nachricht abzurufen.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Messagingaktivitäten, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie Erweiterungspunkte (<xref:System.ServiceModel.Activities.ISendMessageCallback>,  <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in Messagingaktivitäten verwendet werden, um auf <xref:System.ServiceModel.OperationContext.Current%2A> zuzugreifen. Die Rückrufe werden innerhalb der Workflowlaufzeit als eine Implementierung von <xref:System.Activities.IExecutionProperty> registriert, die von den Messagingaktivitäten nach der Ausführung abgerufen wird. Jede Messagingaktivität im gleichen Bereich wie die <xref:System.Activities.IExecutionProperty>-Implementierung ist betroffen. Insbesondere erzwingt dieses Beispiel das Rückrufverhalten mithilfe einer benutzerdefinierten Bereichsaktivität. <xref:System.ServiceModel.Activities.ISendMessageCallback> wird im Clientworkflow verwendet, um <xref:System.Activities.WorkflowApplication.Id%2A> des Workflows als ausgehenden <xref:System.ServiceModel.Channels.MessageHeader> einzuschließen. Dieser Header wird dann im Dienst mit <xref:System.ServiceModel.Activities.IReceiveMessageCallback> abgerufen, und der Wert des Headers wird auf der Konsole ausgegeben.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar. Ausführung dieser Beispiel, die richtige URL-ACLs hinzugefügt werden muss (finden Sie unter [Konfigurieren von HTTP und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) Details), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen von den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um die entsprechenden ACLs hinzuzufügen. Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Sobald die URL-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1.  Erstellen Sie die Projektmappe.  
  
    2.  Legen Sie mehrere Startprojekte fest, von der rechten Maustaste auf die Projektmappe, und wählen **Startprojekte**.  
  
    3.  Hinzufügen **Service** und **Client** (in dieser Reihenfolge) als mehrere Startprojekte.  
  
    4.  Führen Sie die Anwendung aus. Die Clientkonsole zeigt einen Workflow an, der zweimal ausgeführt wird, und das Dienstfenster zeigt die Instanz-ID dieser Workflows an.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
