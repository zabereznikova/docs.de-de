---
title: Aktivitätsbibliothek
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142900"
---
# <a name="activity-library"></a><span data-ttu-id="74e31-102">Aktivitätsbibliothek</span><span class="sxs-lookup"><span data-stu-id="74e31-102">Activity Library</span></span>
<span data-ttu-id="74e31-103">Dieser Abschnitt enthält Beispiele, die erweiterte benutzerdefinierte Aktivitäten in Windows Workflow Foundation (WF) veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="74e31-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74e31-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="74e31-104">In This Section</span></span>

 [<span data-ttu-id="74e31-105">Benutzerdefinierte SendMail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="74e31-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="74e31-106">Veranschaulicht das Erstellen einer benutzerdefinierten Aktivität, die von der <xref:System.Activities.AsyncCodeActivity> abgeleitet wird, um E-Mail-Nachrichten zur Verwendung in einer Workflowanwendung via SMTP zu senden.</span><span class="sxs-lookup"><span data-stu-id="74e31-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="74e31-107">Parallel ForEach (eingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="74e31-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="74e31-108">Veranschaulicht, wie die `ThrottleParallelForEach`-Aktivität der <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität ähnelt, mit der einen Ausnahme, dass sie das Festlegen eines Parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Branches ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="74e31-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="74e31-109">Datenbankzugriffsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="74e31-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="74e31-110">Veranschaulicht, wie Aktivitäten erstellt werden, die den Zugriff auf Datenbanken zum Abrufen oder Ändern von Informationen und zum Verwenden [ADO.NET](../../data/adonet/index.md) für den Zugriff auf die Datenbank ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="74e31-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>  
  
 [<span data-ttu-id="74e31-111">Externalisierte Richtlinienaktivität in .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="74e31-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="74e31-112">Veranschaulicht, wie die ExternalizedPolicy4-Aktivität die Ausführung vorhandener Windows Workflow Foundation in <xref:System.Workflow.Activities.Rules.RuleSet> .NET Framework [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 3.5 (WF 3.5)-Objekten in Windows Workflow Foundation in (WF 4.5) direkt mithilfe des Innasungsmoduls ermöglicht, das in WF 3.5 ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="74e31-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in .NET Framework 3.5 (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span>
  
 [<span data-ttu-id="74e31-113">Nicht generisches ForEach-Element</span><span class="sxs-lookup"><span data-stu-id="74e31-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="74e31-114">Veranschaulicht, wie eine nicht generische Version der <xref:System.Activities.Statements.ForEach%601>-Aktivität erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="74e31-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="74e31-115">ParallelForEach (nicht generisch)</span><span class="sxs-lookup"><span data-stu-id="74e31-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="74e31-116">Veranschaulicht, wie eine nicht generische Version der <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="74e31-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="74e31-117">Abrufen von WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="74e31-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="74e31-118">Veranschaulicht, wie die benutzerdefinierte Aktivität `GetWorkflowInstanceId` verwendet wird, um die Workflowinstanz-ID zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="74e31-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
