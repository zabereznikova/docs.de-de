---
title: WorkflowHostingEndpoint - Lesezeichen-Wiederaufnahme
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1179d09d68d8730847776cf98e3996e3e6817753
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a>WorkflowHostingEndpoint - Lesezeichen-Wiederaufnahme
In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um eine Workflowinstanz zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost>, der in den folgenden Szenarien verwendet werden kann:  
  
-   Erstellen neuer Workflowinstanzen  
  
-   Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.  
  
 Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows und zum Zurückgeben einer Instanz-ID bereitgestellt werden oder mit denen eine Instanz mit einer bestimmten ID erstellt wird. Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz mit einer grundlegenden Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu. Sie ruft dann den `Create`-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Erstellen Sie die Projektmappe.  
  
2.  Führen Sie die Anwendung aus. Die `CreationEndpoint`-Konsole zeigt eine Meldung an, die die Instanz-ID enthält, wenn die Workflowinstanz erstellt wird. Die Meldung "Hello World!" wird vom Workflow bei erfolgreicher Wiederaufnahme des Lesezeichens gedruckt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
