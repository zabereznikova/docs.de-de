---
title: 'Vorgehensweise: Erstellen eines Workflows'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: aaaac74d26421f96a3170b3e5a788145f8ea09fc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704946"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="b80ef-102">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="b80ef-102">How to: Create a Workflow</span></span>
<span data-ttu-id="b80ef-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b80ef-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="b80ef-104">Durchlaufen Sie, dass in die Themen in diesem Abschnitt erstellen einen Workflow, der integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.Flowchart> Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="b80ef-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="b80ef-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="b80ef-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="b80ef-106">Nur eines der Themen in diesem Abschnitt ist erforderlich, um das Lernprogramm abzuschließen. Sie sollten die Methode auswählen, die für Sie von Interesse ist, und die entsprechenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b80ef-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="b80ef-107">Falls gewünscht, können Sie jedoch auch alle Themen durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="b80ef-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b80ef-108">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="b80ef-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="b80ef-109">Um dieses Thema abzuschließen, müssen Sie zuerst abschließen [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="b80ef-109">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b80ef-110">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b80ef-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b80ef-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b80ef-111">In This Section</span></span>  
 [<span data-ttu-id="b80ef-112">Vorgehensweise: Erstellen eines sequenziellen Workflows</span><span class="sxs-lookup"><span data-stu-id="b80ef-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="b80ef-113">Beschreibt, wie Sie einen sequenziellen Workflow mithilfe der <xref:System.Activities.Statements.Sequence>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="b80ef-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="b80ef-114">Vorgehensweise: Erstellen eines Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="b80ef-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="b80ef-115">Beschreibt, wie Sie einen Flussdiagrammworkflow mithilfe der <xref:System.Activities.Statements.Flowchart>-Aktivität erstellen.</span><span class="sxs-lookup"><span data-stu-id="b80ef-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="b80ef-116">Vorgehensweise: Erstellen eines Zustandsautomatenworkflows</span><span class="sxs-lookup"><span data-stu-id="b80ef-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="b80ef-117">Beschreibt das Erstellen eines Zustandsautomatenworkflows mithilfe der <xref:System.Activities.Statements.StateMachine>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b80ef-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b80ef-118">See also</span></span>
- [<span data-ttu-id="b80ef-119">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="b80ef-119">Windows Workflow Foundation Programming</span></span>](programming.md)
