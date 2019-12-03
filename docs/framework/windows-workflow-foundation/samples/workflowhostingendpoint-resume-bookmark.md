---
title: WorkflowHostingEndpoint - Lesezeichen-Wiederaufnahme
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 3b3c7d40a70e797960837c82e2f5a08b2814e17f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710961"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a>WorkflowHostingEndpoint - Lesezeichen-Wiederaufnahme
In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um eine Workflowinstanz zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost>, der in den folgenden Szenarien verwendet werden kann:  
  
- Erstellen neuer Workflowinstanzen  
  
- Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.  
  
 Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows und zum Zurückgeben einer Instanz-ID bereitgestellt werden oder mit denen eine Instanz mit einer bestimmten ID erstellt wird. Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz mit einer grundlegenden Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu. Sie ruft dann den `Create`-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Erstellen Sie die Projektmappe.  
  
2. Führen Sie die Anwendung aus. Die `CreationEndpoint`-Konsole zeigt eine Meldung an, die die Instanz-ID enthält, wenn die Workflowinstanz erstellt wird. Die Meldung "Hallo Welt!" wird vom Workflow bei erfolgreicher Wiederaufnahme des Lesezeichens gedruckt.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
