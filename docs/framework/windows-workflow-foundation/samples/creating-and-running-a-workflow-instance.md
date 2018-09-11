---
title: Erstellen und Ausführen einer Workflowinstanz
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 571d41194ebc98be81646fb5bfdab060225015ca
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270641"
---
# <a name="creating-and-running-a-workflow-instance"></a>Erstellen und Ausführen einer Workflowinstanz
In diesem Beispiel wird gezeigt, wie eine Workflowinstanz ausgeführt wird. Es wird gezeigt, wie sie synchron und asynchron ausgeführt wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Diskussion  
 Im ersten Teil des Beispiels wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> verwendet. Dies ist die einfachste Möglichkeit, einen Workflow auszuführen. Mit <xref:System.Activities.WorkflowInvoker.Invoke%2A> ausgeführte Workflows werden synchron ausgeführt.  
  
 Der zweite Teil des Beispiels verwendet die <xref:System.Activities.WorkflowApplication>-Klasse. <xref:System.Activities.WorkflowApplication> ermöglicht Ihnen eine genauere Kontrolle der einzelnen Instanzen sowie die Interaktion mit dem ausgeführten Workflow und die asynchrone Ausführung des Workflows.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von WorkflowInvoker und WorkflowApplication](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
