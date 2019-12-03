---
title: Erstellen und Ausführen einer Workflowinstanz
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: d895cfa9e924ecf4d1571cf67f1c1e7069e25da5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715203"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="d27e8-102">Erstellen und Ausführen einer Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="d27e8-102">Creating and Running a Workflow Instance</span></span>

<span data-ttu-id="d27e8-103">In diesem Beispiel wird gezeigt, wie eine Workflowinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d27e8-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="d27e8-104">Es wird gezeigt, wie sie synchron und asynchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d27e8-104">It shows how to execute it synchronously and asynchronously.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d27e8-105">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="d27e8-105">Demonstrates</span></span>

<span data-ttu-id="d27e8-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="d27e8-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>

## <a name="discussion"></a><span data-ttu-id="d27e8-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="d27e8-107">Discussion</span></span>

<span data-ttu-id="d27e8-108">Im ersten Teil des Beispiels wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> verwendet.</span><span class="sxs-lookup"><span data-stu-id="d27e8-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="d27e8-109">Dies ist die einfachste Möglichkeit, einen Workflow auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d27e8-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="d27e8-110">Mit <xref:System.Activities.WorkflowInvoker.Invoke%2A> ausgeführte Workflows werden synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d27e8-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>

<span data-ttu-id="d27e8-111">Der zweite Teil des Beispiels verwendet die <xref:System.Activities.WorkflowApplication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d27e8-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="d27e8-112"><xref:System.Activities.WorkflowApplication> ermöglicht Ihnen eine genauere Kontrolle der einzelnen Instanzen sowie die Interaktion mit dem ausgeführten Workflow und die asynchrone Ausführung des Workflows.</span><span class="sxs-lookup"><span data-stu-id="d27e8-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d27e8-113">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d27e8-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d27e8-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d27e8-114">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d27e8-115">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d27e8-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d27e8-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d27e8-116">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a><span data-ttu-id="d27e8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d27e8-117">See also</span></span>

- [<span data-ttu-id="d27e8-118">Verwenden von WorkflowInvoker und WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="d27e8-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../using-workflowinvoker-and-workflowapplication.md)
