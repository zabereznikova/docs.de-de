---
title: Lesezeichenresolver für WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 4676b3c624a7ba1539a7a12ed38c286f688dcf9f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344291"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a>Lesezeichenresolver für WorkflowHostingEndpoint
In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um Workflowinstanzen zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost> , die in den folgenden Szenarien verwendet werden kann:  
  
-   Erstellen neuer Workflowinstanzen  
  
-   Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.  
  
 Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows bereitgestellt werden, und gibt die Instanz-ID zurück oder erstellt eine Instanz mit einer bestimmten ID. Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz mit einer Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu. Sie ruft dann den `Create`-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Erstellen Sie die Projektmappe.  
  
2. Führen Sie die Anwendung aus. Die `CreationEndpoint`-Konsole zeigt eine Meldung an, die die Instanz-ID enthält, wenn die Workflowinstanz erstellt wird. Die Meldung "Hello World!" wird von der Workflowinstanz ausgegeben werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
