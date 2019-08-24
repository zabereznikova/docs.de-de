---
title: Erstellen und Ausführen einer Workflowinstanz
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: fe00ebec8d81e77ff982a36419f1b0a988fcd4ab
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016047"
---
# <a name="creating-and-running-a-workflow-instance"></a>Erstellen und Ausführen einer Workflowinstanz

In diesem Beispiel wird gezeigt, wie eine Workflowinstanz ausgeführt wird. Es wird gezeigt, wie sie synchron und asynchron ausgeführt wird.

## <a name="demonstrates"></a>Veranschaulicht

<xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.

## <a name="discussion"></a>Diskussion

Im ersten Teil des Beispiels wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> verwendet. Dies ist die einfachste Möglichkeit, einen Workflow auszuführen. Mit <xref:System.Activities.WorkflowInvoker.Invoke%2A> ausgeführte Workflows werden synchron ausgeführt.

Der zweite Teil des Beispiels verwendet die <xref:System.Activities.WorkflowApplication>-Klasse. <xref:System.Activities.WorkflowApplication> ermöglicht Ihnen eine genauere Kontrolle der einzelnen Instanzen sowie die Interaktion mit dem ausgeführten Workflow und die asynchrone Ausführung des Workflows.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a>Siehe auch

- [Verwenden von WorkflowInvoker und WorkflowApplication](../using-workflowinvoker-and-workflowapplication.md)
