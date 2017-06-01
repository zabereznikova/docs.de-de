---
title: "Lesezeichenresolver f&#252;r WorkflowHostingEndpoint | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Lesezeichenresolver f&#252;r WorkflowHostingEndpoint
In diesem Beispiel wird veranschaulicht, wie der <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> verwendet werden kann, um Workflowinstanzen zu erstellen.  
  
## Veranschaulicht  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## Diskussion  
 In diesem Beispiel wird <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet, um Workflowinstanzen zu erstellen, die mithilfe von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet werden.<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ist ein Erweiterungspunkt für <xref:System.ServiceModel.Activities.WorkflowServiceHost>, der in den folgenden Szenarien verwendet werden kann:  
  
-   Erstellen neuer Workflowinstanzen  
  
-   Fortsetzen von Lesezeichen für eine auf <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanz.  
  
 Der enthaltene Beispielendpunkt macht einen Vertrag verfügbar, mit dem Vorgänge zum Erstellen eines Workflows bereitgestellt werden, und gibt die Instanz\-ID zurück oder erstellt eine Instanz mit einer bestimmten ID.Die Beispielkonsolenanwendung erstellt eine <xref:System.ServiceModel.Activities.WorkflowServiceHost>\-Instanz mit einer Workflowdefinition und fügt dem Host einen `CreationEndpoint` hinzu.Sie ruft dann den `Create`\-Vorgang auf dem Endpunkt auf, um eine neue Workflowinstanz zu erstellen.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Erstellen Sie die Projektmappe.  
  
2.  Führen Sie die Anwendung aus.Die `CreationEndpoint`\-Konsole zeigt eine Meldung an, die die Instanz\-ID enthält, wenn die Workflowinstanz erstellt wird.Die Meldung "Hello World\!" wird von der Workflowinstanz gedruckt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`