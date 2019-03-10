---
title: Ausnahmen, Transaktionen und Kompensation
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: c4d66e252561ad7b896ff8092e80013c51bd463c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709470"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="91853-102">Ausnahmen, Transaktionen und Kompensation</span><span class="sxs-lookup"><span data-stu-id="91853-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="91853-103">stellt mehrere unterschiedliche Mechanismen für das Behandeln von Laufzeitfehlerbedingungen in Workflows bereit.</span><span class="sxs-lookup"><span data-stu-id="91853-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="91853-104">Workflows können eine Kombination aus Ausnahmehandlern, Transaktionen, Abbruch und Kompensation verwenden, um Fehlerzustände wirksam zu behandeln und eine Wiederherstellung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="91853-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91853-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91853-105">In This Section</span></span>  
 [<span data-ttu-id="91853-106">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="91853-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="91853-107">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TryCatch>-Aktivität Ausnahmen in einem Workflow behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="91853-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="91853-108">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="91853-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="91853-109">Veranschaulicht, wie mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität Transaktionen in einem Workflow verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91853-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="91853-110">Kompensierung</span><span class="sxs-lookup"><span data-stu-id="91853-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="91853-111">Beschreibt die Kompensation in Workflows und veranschaulicht, wie Kompensationsaktivitäten wie <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> und <xref:System.Activities.Statements.Confirm> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91853-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="91853-112">Abbruch</span><span class="sxs-lookup"><span data-stu-id="91853-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="91853-113">Beschreibt, wie die Abbruchbehandlung in Workflows mit integrierten Aktivitäten sowie benutzerdefinierten Aktivitäten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91853-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="91853-114">Debuggen von Workflows</span><span class="sxs-lookup"><span data-stu-id="91853-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="91853-115">Beschreibt das Debugging von Workflows.</span><span class="sxs-lookup"><span data-stu-id="91853-115">Describes how to debug workflows.</span></span>
