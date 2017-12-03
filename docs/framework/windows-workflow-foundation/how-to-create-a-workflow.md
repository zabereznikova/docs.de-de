---
title: 'Vorgehensweise: Erstellen eines Workflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b20ca4258204f938d611f431abc5668b88f167b1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="e9369-102">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="e9369-102">How to: Create a Workflow</span></span>
<span data-ttu-id="e9369-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9369-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="e9369-104">Die Themen in diesem Abschnitt Schritt durch die Erstellung eines Workflows, die sowohl integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.Flowchart> Aktivität und den benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="e9369-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="e9369-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="e9369-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="e9369-106">Nur eines der Themen in diesem Abschnitt ist erforderlich, um das Lernprogramm abzuschließen. Sie sollten die Methode auswählen, die für Sie von Interesse ist, und die entsprechenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="e9369-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="e9369-107">Falls gewünscht, können Sie jedoch auch alle Themen durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="e9369-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9369-108">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="e9369-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="e9369-109">Um dieses Thema abzuschließen, müssen Sie zuerst ausführen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="e9369-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9369-110">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e9369-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9369-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9369-111">In This Section</span></span>  
 [<span data-ttu-id="e9369-112">Vorgehensweise: Erstellen eines sequenziellen Workflows</span><span class="sxs-lookup"><span data-stu-id="e9369-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="e9369-113">Beschreibt, wie Sie einen sequenziellen Workflow mithilfe der <xref:System.Activities.Statements.Sequence>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9369-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="e9369-114">Vorgehensweise: Erstellen eines Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="e9369-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="e9369-115">Beschreibt, wie Sie einen Flussdiagrammworkflow mithilfe der <xref:System.Activities.Statements.Flowchart>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9369-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="e9369-116">Vorgehensweise: Erstellen eines Zustandsautomatenworkflows</span><span class="sxs-lookup"><span data-stu-id="e9369-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="e9369-117">Beschreibt das Erstellen eines Zustandsautomatenworkflows mithilfe der <xref:System.Activities.Statements.StateMachine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e9369-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9369-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9369-118">See Also</span></span>  
 [<span data-ttu-id="e9369-119">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="e9369-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
