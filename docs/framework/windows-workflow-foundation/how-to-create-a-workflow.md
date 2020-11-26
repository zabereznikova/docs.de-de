---
title: 'Vorgehensweise: Erstellen eines Workflows'
description: Führen Sie eine der drei Optionen in diesem Abschnitt aus, um im Rahmen dieses Workflow Foundation-Tutorials einen Workflow zu erstellen.
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 1b2b03d672f86a351bcf36343d6a17e351d40ed0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248785"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="314e1-103">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="314e1-103">How to: Create a Workflow</span></span>

<span data-ttu-id="314e1-104">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="314e1-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="314e1-105">In den Themen in diesem Abschnitt wird Schritt für Schritt erläutert, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Flowchart> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="314e1-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="314e1-106">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="314e1-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="314e1-107">Nur eines der Themen in diesem Abschnitt ist erforderlich, um das Lernprogramm abzuschließen. Sie sollten die Methode auswählen, die für Sie von Interesse ist, und die entsprechenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="314e1-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="314e1-108">Falls gewünscht, können Sie jedoch auch alle Themen durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="314e1-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="314e1-109">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="314e1-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="314e1-110">Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="314e1-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="314e1-111">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="314e1-111">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="314e1-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="314e1-112">In This Section</span></span>  

 [<span data-ttu-id="314e1-113">Vorgehensweise: Erstellen eines sequenziellen Workflows</span><span class="sxs-lookup"><span data-stu-id="314e1-113">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="314e1-114">Beschreibt, wie Sie einen sequenziellen Workflow mithilfe der <xref:System.Activities.Statements.Sequence>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="314e1-114">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="314e1-115">Vorgehensweise: Erstellen eines Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="314e1-115">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="314e1-116">Beschreibt, wie Sie einen Flussdiagrammworkflow mithilfe der <xref:System.Activities.Statements.Flowchart>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="314e1-116">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="314e1-117">Vorgehensweise: Erstellen eines Zustandsautomatworkflows</span><span class="sxs-lookup"><span data-stu-id="314e1-117">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="314e1-118">Beschreibt das Erstellen eines Zustandsautomatenworkflows mithilfe der <xref:System.Activities.Statements.StateMachine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="314e1-118">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314e1-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="314e1-119">See also</span></span>

- [<span data-ttu-id="314e1-120">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="314e1-120">Windows Workflow Foundation Programming</span></span>](programming.md)
