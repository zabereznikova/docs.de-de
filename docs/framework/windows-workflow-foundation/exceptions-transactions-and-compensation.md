---
title: Ausnahmen, Transaktionen und Kompensation
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 346b07cd89c4071088676235d457930637b71549
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512209"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="5531d-102">Ausnahmen, Transaktionen und Kompensation</span><span class="sxs-lookup"><span data-stu-id="5531d-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="5531d-103"> stellt mehrere unterschiedliche Mechanismen für das Behandeln von Laufzeitfehlerbedingungen in Workflows bereit.</span><span class="sxs-lookup"><span data-stu-id="5531d-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="5531d-104">Workflows können eine Kombination aus Ausnahmehandlern, Transaktionen, Abbruch und Kompensation verwenden, um Fehlerzustände wirksam zu behandeln und eine Wiederherstellung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5531d-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5531d-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5531d-105">In This Section</span></span>  
 [<span data-ttu-id="5531d-106">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="5531d-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="5531d-107">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TryCatch>-Aktivität Ausnahmen in einem Workflow behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5531d-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="5531d-108">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="5531d-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="5531d-109">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität Transaktionen in einem Workflow verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5531d-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="5531d-110">Kompensierung</span><span class="sxs-lookup"><span data-stu-id="5531d-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="5531d-111">Beschreibt die Kompensation in Workflows und veranschaulicht, wie Kompensationsaktivitäten wie <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> und <xref:System.Activities.Statements.Confirm> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5531d-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="5531d-112">Abbruch</span><span class="sxs-lookup"><span data-stu-id="5531d-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="5531d-113">Beschreibt, wie die Abbruchbehandlung in Workflows mit integrierten Aktivitäten sowie benutzerdefinierten Aktivitäten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5531d-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="5531d-114">Debuggen von Workflows</span><span class="sxs-lookup"><span data-stu-id="5531d-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="5531d-115">Beschreibt das Debugging von Workflows.</span><span class="sxs-lookup"><span data-stu-id="5531d-115">Describes how to debug workflows.</span></span>
