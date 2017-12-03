---
title: Ausnahmen, Transaktionen und Kompensation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7fab7247540ba4e098a793adebab54ca4219e503
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="846eb-102">Ausnahmen, Transaktionen und Kompensation</span><span class="sxs-lookup"><span data-stu-id="846eb-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="846eb-103"> stellt mehrere unterschiedliche Mechanismen für das Behandeln von Laufzeitfehlerbedingungen in Workflows bereit.</span><span class="sxs-lookup"><span data-stu-id="846eb-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="846eb-104">Workflows können eine Kombination aus Ausnahmehandlern, Transaktionen, Abbruch und Kompensation verwenden, um Fehlerzustände wirksam zu behandeln und eine Wiederherstellung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="846eb-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="846eb-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="846eb-105">In This Section</span></span>  
 [<span data-ttu-id="846eb-106">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="846eb-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="846eb-107">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TryCatch>-Aktivität Ausnahmen in einem Workflow behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="846eb-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="846eb-108">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="846eb-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="846eb-109">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität Transaktionen in einem Workflow verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="846eb-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="846eb-110">Kompensierung</span><span class="sxs-lookup"><span data-stu-id="846eb-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="846eb-111">Beschreibt die Kompensation in Workflows und veranschaulicht, wie Kompensationsaktivitäten wie <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> und <xref:System.Activities.Statements.Confirm> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="846eb-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="846eb-112">Abbruch</span><span class="sxs-lookup"><span data-stu-id="846eb-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="846eb-113">Beschreibt, wie die Abbruchbehandlung in Workflows mit integrierten Aktivitäten sowie benutzerdefinierten Aktivitäten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="846eb-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="846eb-114">Debuggen von Workflows</span><span class="sxs-lookup"><span data-stu-id="846eb-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="846eb-115">Beschreibt das Debugging von Workflows.</span><span class="sxs-lookup"><span data-stu-id="846eb-115">Describes how to debug workflows.</span></span>
