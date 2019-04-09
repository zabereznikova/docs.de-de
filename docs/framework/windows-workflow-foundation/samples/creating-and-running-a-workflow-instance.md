---
title: Erstellen und Ausführen einer Workflowinstanz
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: f2bdfce0b311da6dd20aac5e0fe4f5fbcd14f68a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210096"
---
# <a name="creating-and-running-a-workflow-instance"></a>Erstellen und Ausführen einer Workflowinstanz
In diesem Beispiel wird gezeigt, wie eine Workflowinstanz ausgeführt wird. Es wird gezeigt, wie sie synchron und asynchron ausgeführt wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Diskussion  
 Im ersten Teil des Beispiels wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> verwendet. Dies ist die einfachste Möglichkeit, einen Workflow auszuführen. Mit <xref:System.Activities.WorkflowInvoker.Invoke%2A> ausgeführte Workflows werden synchron ausgeführt.  
  
 Der zweite Teil des Beispiels verwendet die <xref:System.Activities.WorkflowApplication>-Klasse. <xref:System.Activities.WorkflowApplication> ermöglicht es Ihnen, mehr Kontrolle über die einzelnen Instanzen sowie die Möglichkeit, mit dem ausgeführten Workflow interagieren und den Workflow asynchron ausgeführt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von WorkflowInvoker und WorkflowApplication](../using-workflowinvoker-and-workflowapplication.md)
