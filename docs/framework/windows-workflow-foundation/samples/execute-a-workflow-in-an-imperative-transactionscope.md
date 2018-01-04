---
title: "Ausführen eines Workflows in einem imperativen TransactionScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 530a590931a1cb3994406e5605f8da2853ceddaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a><span data-ttu-id="0718e-102">Ausführen eines Workflows in einem imperativen TransactionScope</span><span class="sxs-lookup"><span data-stu-id="0718e-102">Execute a Workflow in an Imperative TransactionScope</span></span>
<span data-ttu-id="0718e-103">In diesem Beispiel wird gezeigt, wie ein Workflow mit <xref:System.Activities.WorkflowInvoker> unter einer <xref:System.Transactions.Transaction> von imperativem C#-Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0718e-103">This sample shows how to execute a workflow using <xref:System.Activities.WorkflowInvoker> under a <xref:System.Transactions.Transaction> from imperative C# code.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="0718e-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="0718e-104">Sample Details</span></span>  
 <span data-ttu-id="0718e-105">In imperativem C#-Code wird der <xref:System.Transactions.TransactionScope> verwendet, um einen Satz von Aufgaben zu kapseln, die unter der gleichen Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0718e-105">In imperative C# code, the <xref:System.Transactions.TransactionScope> is used to encapsulate a set of work that executes under the same transaction.</span></span> <span data-ttu-id="0718e-106">Der <xref:System.Transactions.TransactionScope> funktioniert, indem er eine Ambient-Transaktion erstellt und die <xref:System.Transactions.Transaction.Current%2A>-Eigenschaft initialisiert, auf die dann von beliebigen Aufgaben zugegriffen werden kann, die in diesem Thread ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0718e-106">The <xref:System.Transactions.TransactionScope> works by creating an ambient transaction and initializing the <xref:System.Transactions.Transaction.Current%2A> property, which can then be accessed by any work being executed on that thread.</span></span>  
  
 <span data-ttu-id="0718e-107">Um ein entsprechendes Verhalten im Workflow zu erhalten, muss die Laufzeit die zusätzliche Aufgabe des Initialisierens der <xref:System.Transactions.Transaction.Current%2A> übernehmen, bevor die einzelnen Aktivitäten ausgeführt werden, da ein Workflow keine Threadaffinität zwischen Aktivitäten aufrechterhält.</span><span class="sxs-lookup"><span data-stu-id="0718e-107">To get equivalent behavior in workflow, the runtime has to do the extra work of initializing <xref:System.Transactions.Transaction.Current%2A> before executing each activity because a workflow does not maintain thread affinity between activities.</span></span> <span data-ttu-id="0718e-108">Mit dieser Laufzeitunterstützung ist das resultierende Verhalten, dass alle Aktivitäten garantiert unter dem Kontext der Ambient-Transaktion ausgeführt werden, der vom <xref:System.Activities.WorkflowInvoker> erstellt wird, wenn ein Workflow mit <xref:System.Transactions.TransactionScope> innerhalb eines <xref:System.Transactions.TransactionScope> ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0718e-108">With this runtime support, the resulting behavior is that when executing a workflow with <xref:System.Activities.WorkflowInvoker> inside a <xref:System.Transactions.TransactionScope>, all activities are guaranteed to run under the context of the ambient transaction created by the <xref:System.Transactions.TransactionScope>.</span></span>  
  
 <span data-ttu-id="0718e-109">Ein Workflow kann nur eine einzelne Ambient-Transaktion für jede Workflowinstanz aufweisen; geschachtelte Transaktionen sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0718e-109">A workflow can have only a single ambient transaction for each workflow instance; nested transactions are not available.</span></span> <span data-ttu-id="0718e-110">Auch wenn der Workflow eine <xref:System.Activities.Statements.TransactionScope>-Aktivität enthält, wird dadurch keine neue innere Transaktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="0718e-110">Even if the workflow contains a <xref:System.Activities.Statements.TransactionScope> activity, this does not create a new inner transaction.</span></span> <span data-ttu-id="0718e-111">Stattdessen wird dadurch die Ambient-Transaktion wiederverwendet, die außerhalb des Workflows erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0718e-111">Instead, this reuses the ambient transaction that was created outside the workflow.</span></span>  
  
 <span data-ttu-id="0718e-112">Das Beispiel beginnt einen neuen <xref:System.Transactions.TransactionScope>, druckt die Transaktions-ID und beginnt mit <xref:System.Activities.WorkflowInvoker> einen Workflow.</span><span class="sxs-lookup"><span data-stu-id="0718e-112">The sample begins a new <xref:System.Transactions.TransactionScope>, prints the transaction ID and begins a workflow using <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="0718e-113">Der Workflow druckt die Transaktions-ID erneut und zeigt an, dass es sich um die gleiche Transaktion handelt, führt dann einen <xref:System.Activities.Statements.TransactionScope> aus, und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="0718e-113">The workflow prints the transaction ID again, showing that it is the same transaction, then runs a <xref:System.Activities.Statements.TransactionScope>, then completes.</span></span> <span data-ttu-id="0718e-114">Der <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Anruf bei <xref:System.Activities.WorkflowInvoker> ist synchron, damit der ursprüngliche Thread blockiert wird, bis der Workflow abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0718e-114">The <xref:System.Activities.WorkflowInvoker.Invoke%2A> call on <xref:System.Activities.WorkflowInvoker> is synchronous so the original thread blocks until the workflow completes.</span></span> <span data-ttu-id="0718e-115">Sobald der Workflow vollständig ist, wird die Transaktion abgeschlossen und Ressourcen werden freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0718e-115">Once the workflow is complete, the transaction is completed and resources disposed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0718e-116">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="0718e-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="0718e-117">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ImperativeTransactionSample.sln".</span><span class="sxs-lookup"><span data-stu-id="0718e-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ImperativeTransactionSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="0718e-118">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0718e-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0718e-119">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0718e-119">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0718e-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0718e-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0718e-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0718e-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0718e-122">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0718e-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0718e-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0718e-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`