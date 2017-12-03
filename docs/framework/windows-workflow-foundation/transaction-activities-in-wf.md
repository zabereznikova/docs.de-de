---
title: "Transaktionsaktivitäten in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6c72a54d596468e1ae6948ff9f177e026458628
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="c2776-102">Transaktionsaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="c2776-102">Transaction Activities in WF</span></span>
<span data-ttu-id="c2776-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügt über mehrere vom System bereitgestellte Aktivitäten, um Transaktionen, Kompensationen und Abbrüche zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="c2776-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="c2776-104">Diese Programmiermodelle ermöglichen es dem Workflow, sich weiter vorwärts zu bewegen, falls Änderungen in der Geschäftslogik auftreten oder eine Fehlerbehandlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2776-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c2776-105">Transaktionen, kompensationen und Abbrüche, finden Sie unter [Transaktionen](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Kompensierung](../../../docs/framework/windows-workflow-foundation/compensation.md), und [Abbruch](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="c2776-105"> transactions, compensation, and cancellation, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Compensation](../../../docs/framework/windows-workflow-foundation/compensation.md), and [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="c2776-106">Transaktionsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="c2776-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="c2776-107">Ordnet Abbruchlogik in Form einer Aktivität einem Hauptausführungspfad zu. Wird auch als Aktivität ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="c2776-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="c2776-108">Unterstützt die Kompensation der untergeordneten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="c2776-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="c2776-109">Ruft den Kompensationshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf</span><span class="sxs-lookup"><span data-stu-id="c2776-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="c2776-110">Ruft den Bestätigungshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf</span><span class="sxs-lookup"><span data-stu-id="c2776-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="c2776-111">Demarkiert eine Transaktionsgrenze.</span><span class="sxs-lookup"><span data-stu-id="c2776-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="c2776-112">Legt Bereiche für die Lebensdauer einer Transaktion fest, die von einer empfangenen Meldung initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="c2776-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="c2776-113">Die Transaktion kann in den Workflow der initiierenden Meldung übergeben oder vom Verteiler erstellt werden, wenn die Meldung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="c2776-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="c2776-114">**Hinweis:** der <xref:System.ServiceModel.Activities.TransactedReceiveScope> befindet sich der **Messaging** Teil der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="c2776-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
