---
title: Abrufen von WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 6725ed92bf785e5b7f7d61332944fcce8427388a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778657"
---
# <a name="get-workflowinstanceid"></a>Abrufen von WorkflowInstanceId
In diesem Beispiel wird veranschaulicht, wie die benutzerdefinierte Aktivität `GetWorkflowInstanceId` verwendet wird, um die Workflowinstanz-ID zurückzugeben.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Benutzerdefinierte Aktivitätsentwicklung, Zugriff auf die Workflowinstanz.  
  
## <a name="discussion"></a>Diskussion  
 Für das Abrufen der Instanz-ID eines ausgeführten Workflows muss Code geschrieben werden. Wenn Sie einen vollständig deklarativen Workflow schreiben möchten, benötigen Sie eine Aktivität, die die Workflowinstanz-ID zurückgeben kann, damit im Workflow auf die Aktivität verwiesen werden kann, um eine vollständig deklarative Workflowerstellungserfahrung bereitzustellen. Viele Szenarien erfordern Zugriff auf die Instanz-ID: einige Beispiele dienen Protokollierungs- oder Überwachungszwecken oder der Korrelation auf Anwendungsebene durch Bereitstellen der Instanz-ID für einen Client zurück zur künftigen Zuordnung (z. B. durch Verwendung dieser Aktivität in einer SendReply-Aktivität).  
  
 `GetWorkflowInstanceId` wird als <xref:System.Activities.CodeActivity%601> implementiert, da ein Wert vom Typ <xref:System.Guid> zurückgegeben werden muss und Zugriff auf den <xref:System.Activities.CodeActivityContext> zum Abrufen der Instanz-ID des Workflows erforderlich ist. Die Implementierung ist relativ einfach.  
  
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
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
