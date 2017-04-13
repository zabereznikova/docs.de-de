---
title: "Abrufen von WorkflowInstanceId | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Abrufen von WorkflowInstanceId
In diesem Beispiel wird veranschaulicht, wie die benutzerdefinierte Aktivität `GetWorkflowInstanceId` verwendet wird, um die Workflowinstanz\-ID zurückzugeben.  
  
## Veranschaulicht  
 Benutzerdefinierte Aktivitätsentwicklung, Zugriff auf die Workflowinstanz.  
  
## Diskussion  
 Für das Abrufen der Instanz\-ID eines ausgeführten Workflows muss Code geschrieben werden.Wenn Sie einen vollständig deklarativen Workflow schreiben möchten, benötigen Sie eine Aktivität, die die Workflowinstanz\-ID zurückgeben kann, damit im Workflow auf die Aktivität verwiesen werden kann, um eine vollständig deklarative Workflowerstellungserfahrung bereitzustellen.Viele Szenarien erfordern Zugriff auf die Instanz\-ID: einige Beispiele dienen Protokollierungs\- oder Überwachungszwecken oder der Korrelation auf Anwendungsebene durch Bereitstellen der Instanz\-ID für einen Client zurück zur künftigen Zuordnung \(z. B. durch Verwendung dieser Aktivität in einer SendReply\-Aktivität\).  
  
 `GetWorkflowInstanceId` wird als <xref:System.Activities.CodeActivity%601> implementiert, da ein Wert vom Typ <xref:System.Guid> zurückgegeben werden muss und Zugriff auf den <xref:System.Activities.CodeActivityContext> zum Abrufen der Instanz\-ID des Workflows erforderlich ist.Die Implementierung ist relativ einfach.  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
  
```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`