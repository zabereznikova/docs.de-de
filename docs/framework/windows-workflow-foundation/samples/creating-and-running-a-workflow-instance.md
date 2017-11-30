---
title: "Erstellen und Ausführen einer Workflowinstanz"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d53becfc126f1acee4759ddff956b4435c9aa769
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="4832d-102">Erstellen und Ausführen einer Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="4832d-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="4832d-103">In diesem Beispiel wird gezeigt, wie eine Workflowinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4832d-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="4832d-104">Es wird gezeigt, wie sie synchron und asynchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4832d-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4832d-105">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="4832d-105">Demonstrates</span></span>  
 <span data-ttu-id="4832d-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="4832d-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4832d-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="4832d-107">Discussion</span></span>  
 <span data-ttu-id="4832d-108">Im ersten Teil des Beispiels wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> verwendet.</span><span class="sxs-lookup"><span data-stu-id="4832d-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="4832d-109">Dies ist die einfachste Möglichkeit, einen Workflow auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4832d-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="4832d-110">Mit <xref:System.Activities.WorkflowInvoker.Invoke%2A> ausgeführte Workflows werden synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4832d-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="4832d-111">Der zweite Teil des Beispiels verwendet die <xref:System.Activities.WorkflowApplication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4832d-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="4832d-112"><xref:System.Activities.WorkflowApplication> ermöglicht Ihnen eine genauere Kontrolle der einzelnen Instanzen sowie die Interaktion mit dem ausgeführten Workflow und die asynchrone Ausführung des Workflows.</span><span class="sxs-lookup"><span data-stu-id="4832d-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4832d-113">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4832d-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4832d-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4832d-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4832d-115">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="4832d-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4832d-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4832d-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="4832d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4832d-117">See Also</span></span>  
 [<span data-ttu-id="4832d-118">Verwenden von WorkflowInvoker und WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="4832d-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
