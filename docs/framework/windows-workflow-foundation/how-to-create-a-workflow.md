---
title: 'Vorgehensweise: Erstellen eines Workflows'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7f0bef673ff14ded13306a1fc26e09695601799d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962298"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="59d3e-102">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="59d3e-102">How to: Create a Workflow</span></span>
<span data-ttu-id="59d3e-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="59d3e-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="59d3e-104">In den Themen in diesem Abschnitt wird Schritt für Schritt erläutert, wie Sie einen Workflow erstellen, der integrierte <xref:System.Activities.Statements.Flowchart> Aktivitäten wie die-Aktivität und die benutzerdefinierten [Aktivitäten aus dem vorherigen Abschnitt Gewusst wie: Erstellen Sie ein](how-to-create-an-activity.md) Aktivitäts Thema.</span><span class="sxs-lookup"><span data-stu-id="59d3e-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="59d3e-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="59d3e-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="59d3e-106">Nur eines der Themen in diesem Abschnitt ist erforderlich, um das Lernprogramm abzuschließen. Sie sollten die Methode auswählen, die für Sie von Interesse ist, und die entsprechenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="59d3e-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="59d3e-107">Falls gewünscht, können Sie jedoch auch alle Themen durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="59d3e-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59d3e-108">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="59d3e-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="59d3e-109">Um dieses Thema abzuschließen, müssen Sie zuerst [Folgendes ausführen: Erstellen Sie eine](how-to-create-an-activity.md)Aktivität.</span><span class="sxs-lookup"><span data-stu-id="59d3e-109">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59d3e-110">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="59d3e-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59d3e-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="59d3e-111">In This Section</span></span>  
 [<span data-ttu-id="59d3e-112">Vorgehensweise: Erstellen eines sequenziellen Workflows</span><span class="sxs-lookup"><span data-stu-id="59d3e-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="59d3e-113">Beschreibt, wie Sie einen sequenziellen Workflow mithilfe der <xref:System.Activities.Statements.Sequence>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="59d3e-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="59d3e-114">Vorgehensweise: Erstellen eines Flussdiagramm Workflows</span><span class="sxs-lookup"><span data-stu-id="59d3e-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="59d3e-115">Beschreibt, wie Sie einen Flussdiagrammworkflow mithilfe der <xref:System.Activities.Statements.Flowchart>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="59d3e-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="59d3e-116">Vorgehensweise: Erstellen eines Zustandsautomatworkflows</span><span class="sxs-lookup"><span data-stu-id="59d3e-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="59d3e-117">Beschreibt das Erstellen eines Zustandsautomatenworkflows mithilfe der <xref:System.Activities.Statements.StateMachine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="59d3e-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d3e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59d3e-118">See also</span></span>

- [<span data-ttu-id="59d3e-119">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="59d3e-119">Windows Workflow Foundation Programming</span></span>](programming.md)
