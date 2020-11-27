---
title: Transaktionsaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: c40799f7f0456a13ab975a766a36e9425a2144df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293337"
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="9f0fe-102">Transaktionsaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="9f0fe-102">Transaction Activities in WF</span></span>

<span data-ttu-id="9f0fe-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügt über mehrere vom System bereitgestellte Aktivitäten, um Transaktionen, Kompensationen und Abbrüche zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="9f0fe-104">Diese Programmiermodelle ermöglichen es dem Workflow, sich weiter vorwärts zu bewegen, falls Änderungen in der Geschäftslogik auftreten oder eine Fehlerbehandlung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> <span data-ttu-id="9f0fe-105">Weitere Informationen zu Transaktionen, Kompensation und Abbruch finden Sie unter [Transaktionen](workflow-transactions.md), [Kompensation](compensation.md)und [Abbruch](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="9f0fe-105">For more information about transactions, compensation, and cancellation, see [Transactions](workflow-transactions.md), [Compensation](compensation.md), and [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="9f0fe-106">Transaktionsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="9f0fe-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="9f0fe-107">Ordnet Abbruchlogik in Form einer Aktivität einem Hauptausführungspfad zu. Wird auch als Aktivität ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="9f0fe-108">Unterstützt die Kompensation der untergeordneten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="9f0fe-109">Ruft den Kompensationshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf</span><span class="sxs-lookup"><span data-stu-id="9f0fe-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="9f0fe-110">Ruft den Bestätigungshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf</span><span class="sxs-lookup"><span data-stu-id="9f0fe-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="9f0fe-111">Demarkiert eine Transaktionsgrenze.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="9f0fe-112">Legt Bereiche für die Lebensdauer einer Transaktion fest, die von einer empfangenen Meldung initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="9f0fe-113">Die Transaktion kann in den Workflow der initiierenden Meldung übergeben oder vom Verteiler erstellt werden, wenn die Meldung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="9f0fe-114">**Hinweis:**  Der <xref:System.ServiceModel.Activities.TransactedReceiveScope> befindet sich im Abschnitt **Messaging** der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="9f0fe-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
