---
title: Abrufen von WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 37dc0cac9c6ac69b9e430677a9c8cf3f47b200eb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716022"
---
# <a name="get-workflowinstanceid"></a>Abrufen von WorkflowInstanceId
In diesem Beispiel wird veranschaulicht, wie die benutzerdefinierte Aktivität `GetWorkflowInstanceId` verwendet wird, um die Workflowinstanz-ID zurückzugeben.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Benutzerdefinierte Aktivitätsentwicklung, Zugriff auf die Workflowinstanz.  
  
## <a name="discussion"></a>Diskussion  
 Für das Abrufen der Instanz-ID eines ausgeführten Workflows muss Code geschrieben werden. Wenn Sie einen vollständig deklarativen Workflow schreiben möchten, benötigen Sie eine Aktivität, die die Workflowinstanz-ID zurückgeben kann, damit im Workflow auf die Aktivität verwiesen werden kann, um eine vollständig deklarative Workflowerstellungserfahrung bereitzustellen. Viele Szenarien erfordern Zugriff auf die Instanz-ID: einige Beispiele dienen Protokollierungs- oder Überwachungszwecken oder der Korrelation auf Anwendungsebene durch Bereitstellen der Instanz-ID für einen Client zurück zur künftigen Zuordnung (z. B. durch Verwendung dieser Aktivität in einer SendReply-Aktivität).  
  
 `GetWorkflowInstanceId` wird als <xref:System.Activities.CodeActivity%601> implementiert, da ein Wert vom Typ <xref:System.Guid> zurückgegeben werden muss und Zugriff auf den <xref:System.Activities.CodeActivityContext> zum Abrufen der Instanz-ID des Workflows erforderlich ist. Die Implementierung ist relativ einfach.  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
